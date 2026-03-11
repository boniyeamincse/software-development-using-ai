# Online Learning Solution - Deployment Guide

## 1. Deployment Architecture

### Environment Types

```
Development → Staging → Production → Disaster Recovery
```

**Development**
- Local development environment
- Docker Compose for services
- Shared development database
- Feature testing

**Staging**
- Replica of production
- Separate database and storage
- Full security controls
- Performance testing

**Production**
- High availability setup
- Multi-region deployment
- Auto-scaling enabled
- 99.9% uptime SLA

**Disaster Recovery**
- Hot standby in different region
- Automatic failover
- Regular DR drills

---

## 2. Local Development Setup

### Prerequisites

- Docker & Docker Compose 20.10+
- Node.js 18 LTS+
- Git
- PostgreSQL client tools
- 16GB RAM, 4+ CPU cores recommended

### Setup Steps

```bash
# Clone repository
git clone <repo-url>
cd online-learning-solution

# Setup environment variables
cp .env.example .env.local

# Start services
docker-compose -f docker-compose.dev.yml up -d

# Initialize database
npm run db:migrate
npm run db:seed

# Install dependencies
npm install

# Start development server
npm run dev
```

### Docker Compose Stack (Development)

```yaml
Services:
  - PostgreSQL 14 (port 5432)
  - Redis 7 (port 6379)
  - Elasticsearch 8 (port 9200)
  - RabbitMQ 3.12 (port 5672)
  - MinIO (port 9000)
  - API Server (port 3000)
  - Frontend Dev (port 3001)
  - Mailhog (port 1025)
```

### Environment Configuration

```
# .env.local
NODE_ENV=development
DATABASE_URL=postgresql://user:password@localhost:5432/online_learning_dev
REDIS_URL=redis://localhost:6379
JWT_SECRET=dev-secret-key
AWS_S3_BUCKET=dev-bucket
LOG_LEVEL=debug
```

---

## 3. Staging Deployment

### Infrastructure

**Platform**: AWS / Azure / GCP
**Region**: Same as development team location
**Compute**: 2 application servers (auto-scaling 2-4)
**Database**: RDS PostgreSQL with read replica
**Cache**: ElastiCache Redis
**Storage**: S3 bucket with versioning
**CDN**: CloudFront

### Deployment Process

```bash
# Build Docker image
docker build -t online-learning:staging .
docker tag online-learning:staging ECR_URL/online-learning:staging
docker push ECR_URL/online-learning:staging

# Deploy to staging
kubectl apply -f k8s/staging/

# Run migrations
kubectl exec deployment/api -n staging -- npm run db:migrate

# Verify deployment
kubectl rollout status deployment/api -n staging
```

### Configuration

- **Environment**: Staging
- **Database**: Separate RDS instance
- **Secrets**: AWS Secrets Manager
- **SSL**: Valid SSL certificate (LetsEncrypt)
- **Monitoring**: CloudWatch + Prometheus

### Testing

- Smoke tests post-deployment
- Performance baseline tests
- Security scanning
- Data backup verification

---

## 4. Production Deployment

### Infrastructure Overview

**High-Availability Setup**:
```
┌─────────────────────────────────────┐
│         Load Balancer               │
│      (Auto-scaling traffic)          │
└────────┬────────────────────────────┘
         │
    ┌────┴─────────────────┐
    │                      │
┌───▼───┐             ┌───▼───┐
│ AZ-1  │             │ AZ-2  │
│ App   │             │ App   │
└───┬───┘             └───┬───┘
    │                    │
    └────────┬───────────┘
             │
      ┌──────▼──────┐
      │ Primary DB  │
      └─────┬──────┘
            │
      ┌─────▼─────┐
      │ Replica DB│
      └───────────┘
```

**Compute**:
- Kubernetes cluster (3+ nodes)
- Auto-scaling 5-20 replicas based on load
- Pod affinity for fault tolerance
- Resource limits enforced

**Database**:
- RDS PostgreSQL Multi-AZ
- Automated daily backups (30-day retention)
- Read replicas in different region for DR
- Encryption at rest and in transit
- Parameter group backups

**Storage**:
- S3 bucket with versioning enabled
- Cross-region replication
- Lifecycle policies (archive after 90 days)
- Server-side encryption

**Network**:
- Private subnets for application
- VPC with security groups
- API Gateway / ALB for traffic management
- VPN for admin access

**Monitoring**:
- CloudWatch / Datadog for metrics
- ELK stack for centralized logging
- Prometheus for Kubernetes metrics
- Grafana for dashboards

### Deployment Process

#### Pre-Deployment Checklist

- [ ] Code reviewed and merged to main
- [ ] All tests passing (unit, integration, E2E)
- [ ] Database migrations tested
- [ ] Security scan passed
- [ ] Performance baseline met
- [ ] Release notes prepared
- [ ] Stakeholders notified

#### Deployment Steps

```bash
# 1. Build and push production image
docker build -t online-learning:v1.2.3 .
docker tag online-learning:v1.2.3 ECR_URL/online-learning:v1.2.3
docker push ECR_URL/online-learning:v1.2.3

# 2. Deploy to production (rolling update)
kubectl set image deployment/api \
  api=ECR_URL/online-learning:v1.2.3 \
  -n production

# 3. Monitor rollout
kubectl rollout status deployment/api -n production

# 4. Run database migrations (if needed)
kubectl exec deployment/api -n production -- npm run db:migrate

# 5. Run smoke tests
npm run test:smoke -- https://api.onlinelearning.com

# 6. Monitor application health
# Watch dashboards for errors, latency, resource usage
```

#### Rollback Procedure

```bash
# If issues detected, rollback to previous version
kubectl rollout undo deployment/api -n production

# Verify rollback
kubectl rollout status deployment/api -n production

# Monitor for stability
```

### Production Configuration

```yaml
# kubernetes/production/app-deployment.yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: api
  namespace: production
spec:
  replicas: 10
  strategy:
    type: RollingUpdate
    rollingUpdate:
      maxSurge: 1
      maxUnavailable: 0
  selector:
    matchLabels:
      app: api
  template:
    metadata:
      labels:
        app: api
    spec:
      containers:
      - name: api
        image: ECR_URL/online-learning:latest
        ports:
        - containerPort: 3000
        resources:
          requests:
            cpu: "500m"
            memory: "512Mi"
          limits:
            cpu: "1000m"
            memory: "1Gi"
        livenessProbe:
          httpGet:
            path: /health
            port: 3000
          initialDelaySeconds: 30
          periodSeconds: 10
        readinessProbe:
          httpGet:
            path: /ready
            port: 3000
          initialDelaySeconds: 10
          periodSeconds: 5
        env:
        - name: NODE_ENV
          value: "production"
        - name: DATABASE_URL
          valueFrom:
            secretKeyRef:
              name: prod-secrets
              key: database-url
```

---

## 5. Database Management

### Database Migrations

```bash
# Create migration
npm run db:migrate:create -- --name add_user_preferences

# Run migrations
npm run db:migrate

# Rollback migration
npm run db:migrate:down

# View migration status
npm run db:migrate:status
```

### Backup Strategy

**Daily Backups**:
- Automated snapshots (1 AM UTC)
- Retained for 30 days
- Stored in S3 with encryption
- Cross-region replication

**Weekly Full Backups**:
- Every Sunday 2 AM UTC
- Retained for 90 days
- Stored in separate AWS account

**Disaster Recovery**:
- Test restore monthly
- Recovery Time Objective (RTO): 4 hours
- Recovery Point Objective (RPO): 1 hour

### Database Optimization

```sql
-- Run monthly
ANALYZE;
REINDEX;
VACUUM;

-- Monitor slow queries
SELECT * FROM pg_stat_statements 
ORDER BY total_time DESC 
LIMIT 10;

-- Check table sizes
SELECT 
  schemaname,
  tablename,
  pg_size_pretty(pg_total_relation_size(schemaname||'.'||tablename)) AS size
FROM pg_tables
ORDER BY pg_total_relation_size(schemaname||'.'||tablename) DESC;
```

---

## 6. Environment Variables

### Production Environment Configuration

```bash
# Application
NODE_ENV=production
APP_URL=https://api.onlinelearning.com
CLIENT_URL=https://onlinelearning.com
LOG_LEVEL=info

# Database
DATABASE_URL=postgresql://prod_user:password@prod-db.rds.amazonaws.com:5432/online_learning_prod
DATABASE_POOL_MIN=10
DATABASE_POOL_MAX=30

# Cache & Queue
REDIS_URL=redis://prod-redis.cache.amazonaws.com:6379
RABBITMQ_URL=amqp://user:password@prod-rabbitmq.local:5672

# Authentication
JWT_SECRET=<strong-secret-key>
JWT_EXPIRE=3600
REFRESH_TOKEN_EXPIRE=2592000

# AWS
AWS_REGION=us-east-1
AWS_ACCESS_KEY_ID=<key>
AWS_SECRET_ACCESS_KEY=<secret>
AWS_S3_BUCKET=prod-bucket

# Email
SENDGRID_API_KEY=<key>
SENDGRID_FROM_EMAIL=noreply@onlinelearning.com

# Monitoring
NEW_RELIC_LICENSE_KEY=<key>
SENTRY_DSN=<key>
DATADOG_API_KEY=<key>
```

---

## 7. SSL/TLS Configuration

### Certificate Management

**Automatic Certificate with LetsEncrypt**:
```yaml
# nginx-ingress
apiVersion: cert-manager.io/v1
kind: Certificate
metadata:
  name: api-cert
spec:
  secretName: api-tls
  issuerRef:
    name: letsencrypt-prod
  dnsNames:
  - api.onlinelearning.com
  - api-backup.onlinelearning.com
```

**Certificate Renewal**:
- Automatic via cert-manager
- Renewal before expiry (30 days)
- No downtime during renewal

---

## 8. Monitoring & Alerting

### Key Metrics to Monitor

**Application**:
- Request latency (p50, p95, p99)
- Error rate (4xx, 5xx)
- Throughput (req/sec)
- Active connections

**Infrastructure**:
- CPU utilization (target < 70%)
- Memory usage (target < 80%)
- Disk usage (alert at 85%)
- Network throughput

**Database**:
- Query latency
- Slow query rate
- Connection pool usage
- Replication lag

**Business**:
- Active students
- Course enrollments
- Assessment submissions
- Certificate issuances

### Alert Thresholds

| Metric | Warning | Critical |
|--------|---------|----------|
| Error Rate | > 1% | > 5% |
| Latency (p99) | > 1000ms | > 5000ms |
| CPU | > 70% | > 90% |
| Memory | > 80% | > 95% |
| Disk | > 85% | > 95% |
| DB Replication Lag | > 60s | > 300s |

---

## 9. Scaling Considerations

### Horizontal Scaling

- **API servers**: Auto-scale 5-20 based on CPU/Memory
- **Database**: Read replicas for query distribution
- **Cache**: Cluster mode Redis for high throughput
- **Storage**: S3 auto-scales (no configuration needed)

### Vertical Scaling

- **Node type**: Upgrade instance types during off-peak
- **Database**: Increase storage and compute as needed
- **Memory**: Increase caching layer capacity

### Load Distribution

- **Geographic**: Multi-region deployment
- **Time-based**: Scale up during peak hours (evenings)
- **Content type**: Separate compute for video streaming

---

## 10. Disaster Recovery

### DR Strategy

**RPO**: 1 hour
**RTO**: 4 hours
**Backup locations**: Primary + Secondary region

### Failover Procedure

1. **Detect primary region failure** (automated monitoring)
2. **Fail over DNS** to secondary region (AWS Route53 failover)
3. **Activate hot standby** database and application
4. **Verify functionality** (smoke tests)
5. **Notify stakeholders**
6. **Begin recovery** of primary infrastructure

### DR Testing

- Monthly DR drills
- Restore from backup to test environment
- Document all issues and improvements
- Update runbooks based on findings

---

## 11. Post-Deployment Checklist

- [ ] All services responding (health checks passing)
- [ ] Database migrations completed successfully
- [ ] API endpoints returning expected responses
- [ ] Frontend loads without errors
- [ ] Authentication/authorization working
- [ ] File uploads/downloads functioning
- [ ] Email notifications sending
- [ ] Logs flowing to centralized logging
- [ ] Monitoring and alerts active
- [ ] Performance baseline met
- [ ] No critical security issues
- [ ] Users can complete critical workflows

---

## 12. Troubleshooting

### Common Issues

**Pod CrashLoopBackOff**
```bash
# Check logs
kubectl logs <pod-name> -n production

# Check events
kubectl describe pod <pod-name> -n production

# Check resource limits
kubectl top pods -n production
```

**Database Connection Failures**
```bash
# Check connectivity
psql postgresql://user:pass@host/db -c "SELECT 1"

# Check connection pool
SELECT count(*) FROM pg_stat_activity;
```

**Memory Leaks**
- Monitor memory growth over time
- Use heap snapshots
- Analyze with Chrome DevTools
- Profile with clinic.js

**Slow Queries**
- Enable query logging
- Analyze with EXPLAIN ANALYZE
- Create appropriate indexes
- Consider query optimization

