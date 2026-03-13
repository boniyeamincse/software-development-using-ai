# 10 - Yoga Studio Technology Stack

## Core Engineering
- **Backend API**: Node.js (TypeScript) or Go for high-speed booking and community feed logic.
- **Frontend (Web)**: Next.js (React) for administrative and teacher-facing portals.
- **Frontend (Mobile)**: React Native for a beautiful, cross-platform student experience.

## Engagement & Social
- **Real-Time Feed**: WebSockets (Socket.io) or Pusher for live social updates and booking status.
- **Notifications**: OneSignal (Push/SMS) for reminders and studio updates.
- **Media Hosting**: Cloudinary or AWS S3 for hosting teacher-training videos and meditation audio.

## Data & Infrastructure
- **Primary DB**: PostgreSQL (RDS or Supabase) for student data and financials.
- **Cache Layer**: Redis for real-time class capacity and leaderboard counts.
- **Payments**: Stripe (Connect) for seamless membership billing and teacher payouts.

## Deployment
- **Platform**: Vercel (Frontends) and AWS (Backend) for scalable boutique operations.
- **Monitoring**: Sentry for error tracking + Google Analytics for app usage trends.

---
[← Previous: System Workflows](09-workflow.md) | [Back to Index](README.md) | [Next: Security & Compliance →](11-security.md)
