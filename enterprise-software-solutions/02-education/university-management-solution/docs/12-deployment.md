# 12 - University Deployment

## Multi-Region Availability
To support international campuses and ensure reliability:
- **Active-Active Deployment**: Hosted across two geographic regions.
- **Failover**: Automated traffic rerouting via DNS if a regional data center goes offline.

## Zero-Downtime Updates
- **Canary Releases**: Deploying new registrar logic to 5% of users first to monitor for errors.
- **Database Migrations**: Performed using staggered, non-locking scripts.
