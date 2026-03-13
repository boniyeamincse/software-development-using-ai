# 12 - Deployment Strategy

## Environments
- **Development**: Local environment for features.
- **Staging**: Replica of production for final testing.
- **Production**: Live environment hosted on AWS.

## Deployment Steps
1. Push code to `main` branch.
2. GitHub Action triggers automated tests and linting.
3. Build Docker images and push to ECR.
4. Update Kubernetes manifest / ECS Service.
5. Run database migrations.
6. Blue/Green deployment for zero-downtime.

## Scalability
- **Auto-scaling**: Automatically spin up more instances during peak hours (e.g., Result day).
- **Global CDN**: Use CloudFront to serve static assets with low latency globally.
