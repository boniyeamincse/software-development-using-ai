# 12 - Exam Deployment Strategy

## Peak Load Scaling
Exam days create "Traffic Spikes" (e.g., millions of hits at 9:00 AM).
- **Pre-warming**: Scaling up server clusters 30 minutes before the scheduled exam start.
- **Database read-replicas**: Offloading report generation and dashboard views to secondary nodes.

## Disaster Recovery
- **Disconnected Mode**: Allowing the assessment app to work locally if the internet drops for < 5 minutes, syncing back once restored.
- **Multi-Cloud Failover**: Secondary deployment on GCP if AWS experiences a regional outage.

---
[← Previous: Security & Compliance](11-security.md) | [Back to Index](README.md) | [Next: Roadmap & Future Enhancements →](13-future-features.md)
