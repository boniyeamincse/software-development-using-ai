# 05 - Parent Communication Architecture

## Mobile-First & Real-Time Design
The system is built on a **Globally Distributed WebSocket Architecture** to ensure that notifications and translations are near-instant.

## Technical Components
- **Client**: Native Flutter apps for iOS/Android and a React-based web admin.
- **Messaging Core**: Node.js/Socket.io for low-latency bidirectional communication.
- **Translation Bridge**: Integration with Google Cloud Translation or Amazon Translate APIs.
- **Push Engine**: Firebase Cloud Messaging (FCM) and Apple Push Notification service (APNs).

## Performance Tier
- **Redis Pub/Sub**: To scale WebSocket connections across multiple server instances.
- **Elasticsearch**: For high-speed keyword search inside private and group message histories.

---
[← Previous: User Roles & Permissions](04-user-roles.md) | [Back to Index](README.md) | [Next: Database Design →](06-database-design.md)
