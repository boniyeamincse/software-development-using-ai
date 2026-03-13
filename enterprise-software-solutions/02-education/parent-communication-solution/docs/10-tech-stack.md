# 10 - Parent Communication Tech Stack

## Communication Core
- **Messaging**: Socket.io (Node.js) & MQTT for IoT alerts.
- **Push**: Firebase Cloud Messaging (FCM).
- **Translation**: Google Cloud Translation API.

## Frontend & Mobile
- **Mobile**: Flutter (iOS & Android).
- **Web Admin**: Next.js / Tailwind CSS.

## Data & Backend
- **Primary DB**: PostgreSQL with JSONB (for polymorphic message payloads).
- **Cache/Socket Sync**: Redis.
- **Compute**: AWS Fargate (for consistent WebSocket connection management).
