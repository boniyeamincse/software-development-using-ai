# 10 - Wellness Technology Stack

## Core Development
- **Backend API**: Node.js (TypeScript) or Go.
- **Frontend (Web)**: Next.js (React) for admin and HR tools.
- **Frontend (Mobile)**: React Native or Flutter (for cross-platform health-data access).

## Health & Engagement
- **Device Sync**: Integration with specialized providers like Terra, Vital, or Human API.
- **Real-Time**: WebSockets for leaderboard updates and live social feeds.
- **Notifications**: OneSignal or Firebase Cloud Messaging (FCM).

## Data & Infrastructure
- **Primary DB**: AWS Aurora PostgreSQL (Relational).
- **Activity Stream**: TimescaleDB for time-series health metrics.
- **Cache**: Redis for social rankings and session state.

## Deployment
- **Platform**: AWS Multi-Region with auto-scaling to handle high-traffic social events.
- **CI/CD**: GitHub Actions for automated unit and integration tests.

---
[← Previous: System Workflows](09-workflow.md) | [Back to Index](README.md) | [Next: Security & Compliance →](11-security.md)
