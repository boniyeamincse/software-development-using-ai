# School Management System - Deployment

## 1. Deployment Overview

This document provides comprehensive instructions for deploying the School Management System to production, staging, and development environments.

---

## 2. Pre-Deployment Checklist

### 2.1 Code Readiness

- [ ] All tests passing (unit, integration, E2E)
- [ ] Code review completed
- [ ] No hardcoded secrets or credentials
- [ ] Environment-specific configuration prepared
- [ ] Database migrations tested
- [ ] Dependencies documented and locked
- [ ] Performance optimization completed
- [ ] Security scan passed

### 2.2 Infrastructure Readiness

- [ ] Server provisioned (minimum 4 CPU, 8GB RAM)
- [ ] Database server setup (MySQL 8.0+)
- [ ] Redis server configured
- [ ] SSL/TLS certificate obtained
- [ ] Domain name configured
- [ ] CDN setup (optional)
- [ ] Backup storage prepared
- [ ] Monitoring tools configured

### 2.3 Documentation Readiness

- [ ] API documentation complete
- [ ] Deployment guide prepared
- [ ] Rollback procedures documented
- [ ] Emergency contacts listed
- [ ] Support contacts identified

---

## 3. Local Development Setup

### 3.1 Prerequisites

```bash
# Required software
- Git (v2.30+)
- Docker & Docker Compose
- PHP 8.1+ (if not using Docker)
- Node.js 18+ (for frontend build)
- Composer (PHP dependency manager)
- npm or yarn (JavaScript package manager)
```

### 3.2 Local Development Installation

#### Step 1: Clone Repository
```bash
git clone https://github.com/yourorg/school-management-system.git
cd school-management-system
```

#### Step 2: Setup Environment

**For Docker-based setup:**
```bash
# Copy example environment file
cp .env.example .env

# Update .env with local values
# (Database, API keys, etc.)

# Start containers
docker-compose up -d

# Run migrations
docker-compose exec app php artisan migrate

# Seed database (optional)
docker-compose exec app php artisan db:seed
```

**For Manual setup (PHP/Laravel):**
```bash
# Install dependencies
composer install
npm install

# Generate application key
php artisan key:generate

# Setup database
cp .env.example .env
# Edit .env with database credentials

# Run migrations
php artisan migrate

# Seed database
php artisan db:seed

# Build assets
npm run dev

# Start development server
php artisan serve
```

#### Step 3: Verify Installation
```bash
# Check application
curl http://localhost:8000/api/v1/health

# Access application
# http://localhost:8000

# Run tests
php artisan test
npm run test
```

---

## 4. Testing Environment Setup

### 4.1 Staging Environment

**Purpose**: Mirror production, test before release

```bash
# Deploy to staging
./deploy.sh staging

# Run full test suite
npm run test:e2e
php artisan test --env=testing

# Performance testing
ab -n 1000 -c 10 https://staging.schoolms.com/

# Security testing
# Run OWASP ZAP
# Run penetration tests
```

### 4.2 Environment Variables

**Testing .env**
```env
APP_ENV=testing
APP_DEBUG=true
APP_KEY=base64:xxxxx

DB_HOST=localhost
DB_DATABASE=school_ms_test
DB_USERNAME=test_user
DB_PASSWORD=test_password

REDIS_HOST=localhost
REDIS_PORT=6379

MAIL_DRIVER=log
PAYMENT_GATEWAY=sandbox
```

---

## 5. Production Deployment

### 5.1 Server Requirements

#### Minimum Configuration
- **CPU**: 4 cores
- **RAM**: 8 GB
- **Storage**: 100 GB SSD
- **Bandwidth**: 1 Gbps
- **OS**: Ubuntu 22.04 LTS or CentOS 8

#### Recommended Configuration
- **CPU**: 8+ cores
- **RAM**: 16+ GB
- **Storage**: 250+ GB SSD
- **Bandwidth**: 10 Gbps
- **OS**: Ubuntu 22.04 LTS

### 5.2 Cloud Deployment (AWS Example)

#### Step 1: Infrastructure Setup

```bash
# Create VPC
aws ec2 create-vpc --cidr-block 10.0.0.0/16

# Create security groups
aws ec2 create-security-group \
  --group-name web-sg \
  --description "Web server security group" \
  --vpc-id vpc-xxxxx

# Open ports
aws ec2 authorize-security-group-ingress \
  --group-id sg-xxxxx \
  --protocol tcp --port 80 --cidr 0.0.0.0/0
aws ec2 authorize-security-group-ingress \
  --group-id sg-xxxxx \
  --protocol tcp --port 443 --cidr 0.0.0.0/0
```

#### Step 2: Create Database

```bash
# Create RDS MySQL instance
aws rds create-db-instance \
  --db-instance-identifier school-ms-db \
  --db-instance-class db.t3.medium \
  --engine mysql \
  --engine-version 8.0.28 \
  --master-username admin \
  --master-user-password secure_password \
  --allocated-storage 100
```

#### Step 3: Launch Application Server

```bash
# Create EC2 instance
aws ec2 run-instances \
  --image-id ami-xxxxx \
  --instance-type t3.medium \
  --key-name my-key \
  --security-group-ids sg-xxxxx \
  --user-data file://init-script.sh
```

#### Step 4: Setup Load Balancer

```bash
# Create ALB
aws elbv2 create-load-balancer \
  --name school-ms-alb \
  --subnets subnet-xxxxx subnet-yyyyy \
  --security-groups sg-xxxxx

# Create target group
aws elbv2 create-target-group \
  --name school-ms-targets \
  --protocol HTTP \
  --port 80 \
  --vpc-id vpc-xxxxx
```

### 5.3 Docker Deployment

#### Step 1: Build Docker Image

```dockerfile
# Dockerfile
FROM php:8.1-fpm

WORKDIR /app

# Install dependencies
RUN apt-get update && apt-get install -y \
    libpq-dev \
    libpng-dev \
    libjpeg-dev \
    && docker-php-ext-install pdo_mysql gd

# Copy application
COPY . .

# Install PHP dependencies
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN composer install --no-dev --optimize-autoloader

# Build assets
RUN npm install && npm run production

# Set permissions
RUN chown -R www-data:www-data /app/storage

EXPOSE 9000

CMD ["php-fpm"]
```

#### Step 2: Build and Push Image

```bash
# Build image
docker build -t school-ms:1.0.0 .

# Tag image
docker tag school-ms:1.0.0 your-registry.com/school-ms:1.0.0

# Push to registry
docker push your-registry.com/school-ms:1.0.0
```

#### Step 3: Deploy with Docker Compose

```yaml
# docker-compose.yml (Production)
version: '3.8'

services:
  app:
    image: your-registry.com/school-ms:1.0.0
    ports:
      - "9000:9000"
    environment:
      - DB_HOST=db
      - DB_DATABASE=school_ms
      - DB_USERNAME=app_user
      - DB_PASSWORD=${DB_PASSWORD}
      - REDIS_HOST=redis
    depends_on:
      - db
      - redis
    networks:
      - app-network
    restart: always
    healthcheck:
      test: ["CMD", "curl", "-f", "http://localhost:9000"]
      interval: 30s
      timeout: 10s
      retries: 3

  web:
    image: nginx:latest
    ports:
      - "80:80"
      - "443:443"
    volumes:
      - ./nginx.conf:/etc/nginx/nginx.conf:ro
      - ./ssl:/etc/nginx/ssl:ro
    depends_on:
      - app
    networks:
      - app-network
    restart: always

  db:
    image: mysql:8.0
    environment:
      - MYSQL_DATABASE=school_ms
      - MYSQL_USER=app_user
      - MYSQL_PASSWORD=${DB_PASSWORD}
      - MYSQL_ROOT_PASSWORD=${DB_ROOT_PASSWORD}
    volumes:
      - db-data:/var/lib/mysql
    networks:
      - app-network
    restart: always
    healthcheck:
      test: ["CMD", "mysqladmin", "ping", "-h", "localhost"]
      interval: 30s
      timeout: 10s
      retries: 3

  redis:
    image: redis:7-alpine
    networks:
      - app-network
    restart: always

volumes:
  db-data:

networks:
  app-network:
    driver: bridge
```

### 5.4 Kubernetes Deployment

#### Step 1: Create Namespace

```bash
kubectl create namespace school-ms
```

#### Step 2: Create ConfigMap & Secrets

```bash
# Create ConfigMap
kubectl create configmap app-config \
  --from-literal=APP_ENV=production \
  --from-literal=APP_DEBUG=false \
  -n school-ms

# Create Secrets
kubectl create secret generic db-secret \
  --from-literal=DB_PASSWORD=secure_password \
  -n school-ms

kubectl create secret generic app-secret \
  --from-literal=APP_KEY=base64:xxxxx \
  -n school-ms
```

#### Step 3: Deploy Application

```yaml
# app-deployment.yml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: school-ms-app
  namespace: school-ms
spec:
  replicas: 3
  selector:
    matchLabels:
      app: school-ms
  template:
    metadata:
      labels:
        app: school-ms
    spec:
      containers:
      - name: app
        image: your-registry.com/school-ms:1.0.0
        ports:
        - containerPort: 9000
        env:
        - name: DB_HOST
          value: "db-service"
        - name: REDIS_HOST
          value: "redis-service"
        - name: DB_PASSWORD
          valueFrom:
            secretKeyRef:
              name: db-secret
              key: DB_PASSWORD
        resources:
          requests:
            cpu: 100m
            memory: 256Mi
          limits:
            cpu: 500m
            memory: 512Mi
        livenessProbe:
          httpGet:
            path: /health
            port: 9000
          initialDelaySeconds: 30
          periodSeconds: 10
        readinessProbe:
          httpGet:
            path: /health
            port: 9000
          initialDelaySeconds: 20
          periodSeconds: 5
```

#### Step 4: Create Service

```yaml
# app-service.yml
apiVersion: v1
kind: Service
metadata:
  name: school-ms-service
  namespace: school-ms
spec:
  type: LoadBalancer
  selector:
    app: school-ms
  ports:
  - protocol: TCP
    port: 80
    targetPort: 9000
```

#### Step 5: Deploy

```bash
# Deploy
kubectl apply -f app-deployment.yml
kubectl apply -f app-service.yml

# Verify
kubectl get pods -n school-ms
kubectl get services -n school-ms

# Check logs
kubectl logs -f deployment/school-ms-app -n school-ms

# Scale
kubectl scale deployment school-ms-app --replicas=5 -n school-ms
```

---

## 6. Database Setup

### 6.1 Initial Database Setup

```bash
# Create database
mysql -u root -p
CREATE DATABASE school_ms;
CREATE USER 'app_user'@'localhost' IDENTIFIED BY 'secure_password';
GRANT ALL PRIVILEGES ON school_ms.* TO 'app_user'@'localhost';
FLUSH PRIVILEGES;
```

### 6.2 Run Migrations

```bash
# Run all migrations
php artisan migrate --env=production

# Seed database (optional)
php artisan db:seed --env=production

# Verify
php artisan migrate:status
```

### 6.3 Database Backup

```bash
# Manual backup
mysqldump -u app_user -p school_ms > backup_$(date +%Y%m%d_%H%M%S).sql

# Automated backup (cron)
0 2 * * * mysqldump -u app_user -p school_ms | gzip > /backups/school_ms_$(date +\%Y\%m\%d_\%H\%M\%S).sql.gz
```

---

## 7. HTTPS/SSL Setup

### 7.1 Obtain SSL Certificate

```bash
# Using Let's Encrypt with Certbot
sudo apt update
sudo apt install certbot python3-certbot-nginx

# Generate certificate
sudo certbot certonly --standalone -d schoolms.com -d www.schoolms.com

# Auto-renewal
sudo systemctl enable certbot.timer
sudo systemctl start certbot.timer
```

### 7.2 Configure Nginx

```nginx
# /etc/nginx/sites-available/school-ms

server {
    listen 80;
    server_name schoolms.com www.schoolms.com;
    return 301 https://$server_name$request_uri;
}

server {
    listen 443 ssl http2;
    server_name schoolms.com www.schoolms.com;

    ssl_certificate /etc/letsencrypt/live/schoolms.com/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/schoolms.com/privkey.pem;
    
    ssl_protocols TLSv1.2 TLSv1.3;
    ssl_ciphers HIGH:!aNULL:!MD5;
    ssl_prefer_server_ciphers on;

    # Security headers
    add_header Strict-Transport-Security "max-age=31536000; includeSubDomains" always;
    add_header X-Frame-Options "SAMEORIGIN" always;
    add_header X-Content-Type-Options "nosniff" always;
    add_header X-XSS-Protection "1; mode=block" always;

    root /var/www/school-ms/public;
    index index.php index.html;

    location ~ \.php$ {
        fastcgi_pass unix:/var/run/php-fpm.sock;
        fastcgi_index index.php;
        include fastcgi_params;
    }

    location / {
        try_files $uri $uri/ /index.php?$query_string;
    }
}
```

---

## 8. Environment Configuration

### 8.1 Production .env

```env
APP_NAME="School Management System"
APP_ENV=production
APP_DEBUG=false
APP_URL=https://schoolms.com
APP_KEY=base64:xxxxxxxxxxxxxxxxxxxxx

# Database
DB_CONNECTION=mysql
DB_HOST=db.schoolms.com
DB_PORT=3306
DB_DATABASE=school_ms
DB_USERNAME=app_user
DB_PASSWORD=secure_password_here

# Redis
REDIS_HOST=redis.schoolms.com
REDIS_PORT=6379
REDIS_PASSWORD=redis_password

# Mail
MAIL_MAILER=smtp
MAIL_HOST=smtp.sendgrid.net
MAIL_PORT=587
MAIL_USERNAME=apikey
MAIL_PASSWORD=sendgrid_api_key
MAIL_FROM_ADDRESS=noreply@schoolms.com
MAIL_FROM_NAME="School Management System"

# AWS S3 (for file uploads)
AWS_ACCESS_KEY_ID=your_access_key
AWS_SECRET_ACCESS_KEY=your_secret_key
AWS_DEFAULT_REGION=us-east-1
AWS_BUCKET=school-ms-files

# Payment Gateway
STRIPE_PUBLIC_KEY=pk_live_xxxxx
STRIPE_SECRET_KEY=sk_live_xxxxx

# Monitoring
SENTRY_DSN=https://xxxxx@sentry.io/1234567

# Two-Factor Auth
TWILIO_ACCOUNT_SID=your_account_sid
TWILIO_AUTH_TOKEN=your_auth_token
TWILIO_FROM_NUMBER=+1234567890
```

---

## 9. Post-Deployment

### 9.1 Health Checks

```bash
# Check application health
curl https://schoolms.com/api/v1/health

# Check database connection
php artisan tinker
>>> DB::connection()->getPdo()

# Check Redis connection
redis-cli ping

# Check file permissions
ls -la /var/www/school-ms/storage
```

### 9.2 Monitoring Setup

```bash
# Install monitoring agents
# New Relic, DataDog, or Prometheus + Grafana

# Configure log aggregation
# ELK Stack, Splunk, or CloudWatch

# Setup alerting
# PagerDuty, Slack, or Email notifications
```

### 9.3 Backup Verification

```bash
# Test backup restoration
mysql -u root -p school_ms < latest_backup.sql

# Verify data integrity
php artisan tinker
>>> Student::count() // Should return correct count
```

---

## 10. Deployment Automation

### 10.1 GitHub Actions CI/CD

```yaml
# .github/workflows/deploy.yml
name: Deploy to Production

on:
  push:
    branches: [main]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      
      - name: Run tests
        run: |
          composer install
          php artisan test
      
      - name: Build assets
        run: npm ci && npm run production
      
      - name: Deploy to server
        env:
          DEPLOY_KEY: ${{ secrets.DEPLOY_KEY }}
        run: |
          mkdir -p ~/.ssh
          echo "$DEPLOY_KEY" > ~/.ssh/id_rsa
          chmod 600 ~/.ssh/id_rsa
          ssh-keyscan -H ${{ secrets.SERVER_IP }} >> ~/.ssh/known_hosts
          ssh ubuntu@${{ secrets.SERVER_IP }} 'cd /var/www/school-ms && git pull origin main && php artisan migrate --force'
      
      - name: Smoke tests
        run: curl -f https://schoolms.com/api/v1/health || exit 1
```

---

## 11. Rollback Procedures

### 11.1 Rollback Steps

```bash
# 1. Stop new version
docker-compose down

# 2. Revert code
git revert HEAD
git push origin main

# 3. Restore database backup
mysql -u root -p school_ms < /backups/school_ms_before_deployment.sql

# 4. Restart with previous version
docker-compose up -d

# 5. Verify
curl https://schoolms.com/api/v1/health
```

### 11.2 Zero-Downtime Deployment

```bash
# Blue-green deployment
# 1. Deploy new version to green environment
# 2. Run smoke tests
# 3. Switch traffic to green
# 4. Keep blue as rollback
```

---

## 12. Performance Optimization

### 12.1 Caching

```bash
# Clear application cache
php artisan cache:clear
php artisan config:cache
php artisan route:cache
php artisan view:cache

# Optimize autoloader
composer install --optimize-autoloader --no-dev
```

### 12.2 Database Optimization

```sql
-- Analyze tables
ANALYZE TABLE students;
ANALYZE TABLE attendance_records;
ANALYZE TABLE results;

-- Optimize tables
OPTIMIZE TABLE students;
```

### 12.3 CDN Configuration

```bash
# Push static assets to CDN
aws s3 sync ./public/assets s3://my-bucket/assets/ --cache-control max-age=31536000

# Update URLs in application
APP_URL=https://cdn.schoolms.com
```

---

## 13. Maintenance & Updates

### 13.1 Scheduled Maintenance

```bash
# Weekly
- Backup verification
- Log review
- Performance check

# Monthly
- Security updates
- Dependency updates
- Database optimization

# Quarterly
- Full penetration test
- Disaster recovery drill
- Capacity planning review
```

### 13.2 Update Procedure

```bash
# 1. Backup
mysqldump -u root -p school_ms > backup_pre_update.sql

# 2. Test in staging
git checkout v2.0.0-rc1
php artisan migrate
php artisan test

# 3. Deploy to production
git checkout v2.0.0
git pull
php artisan migrate --force
php artisan cache:clear

# 4. Verify
curl https://schoolms.com/api/v1/health
```

---

## 14. Deployment Checklist

### Pre-Deployment
- [ ] All tests passing
- [ ] Code reviewed
- [ ] Database migrations ready
- [ ] Backup created
- [ ] Team notified
- [ ] Rollback plan prepared

### During Deployment
- [ ] Monitor application logs
- [ ] Check error rates
- [ ] Monitor resource usage
- [ ] Check database performance
- [ ] Verify user reports

### Post-Deployment
- [ ] Run smoke tests
- [ ] Verify critical features
- [ ] Check performance metrics
- [ ] Review error logs
- [ ] Confirm backup created
- [ ] Document deployment details

---

## Summary

Deployment involves:
- **Local development** setup
- **Staging environment** for testing
- **Production deployment** (Docker/Kubernetes/Cloud)
- **Database setup** and migrations
- **SSL/HTTPS** configuration
- **Monitoring** and alerting
- **Automated CI/CD** pipeline
- **Rollback procedures** for safety
- **Regular backups** and testing

