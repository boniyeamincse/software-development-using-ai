# 12 - Homework Deployment Strategy

## Elastic Scaling
- **Dead-Hour Scheduling**: Background tasks like "Weekly Parent Reports" run during nighttime low-traffic hours.
- **Auto-Scaling Groups**: To handle "The Sunday Night Peak" (when most weekly homework is due).

## Global Availability
- **Multi-Region S3**: Store files in the region closest to the school to ensure fast upload speeds.
- **CDN**: Cloudfront for fast delivery of teacher-uploaded videos.
