# 10 - Time Technology Stack

## Core Engineering
- **Backend API**: Node.js (High-speed event handling).
- **Frontend**: Next.js (React).
- **Mobile**: Flutter or React Native.
- **Desktop**: Electron.

## Persistence & State
- **Primary DB**: PostgreSQL.
- **Timer State**: Redis (for speed and heartbeat management).
- **Caching**: CDN for public project/task metadata.

## Infrastructure
- **Hosting**: AWS with Lambda for cost-effective report generation.
- **Monitoring**: Datadog (for tracking timer heartbeat latency).
- **Security**: AWS Secrets Manager for managing 3rd-party banking/HR credentials.
