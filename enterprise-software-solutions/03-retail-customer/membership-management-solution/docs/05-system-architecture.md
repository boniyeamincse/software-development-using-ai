# 05 - Membership System Architecture

## Reliability & Real-Time Sync
The system is built on a **Modular Subscription Architecture** designed for high uptime and rapid synchronization with physical access hardware.

## Technical Infrastructure
- **Frontend**: Next.js (Portal) and React (Admin). Native mobile apps for digital cards.
- **Backend API**: Node.js (NestJS) or C# (.NET Core) for robust business logic.
- **Biling Logic**: Integration with Stripe Billing or Recurly for recurring logic.
- **Real-time Bridge**: MQTT or AWS IoT Core for syncing status to physical gates.

## Performance Tier
- **State Store (Redis)**: For sub-second access-token verification at the entry point.
- **Relational DB (PostgreSQL)**: Storing the core member database and plan history.

---
[← Previous: User Roles & Permissions](04-user-roles.md) | [Back to Index](README.md) | [Next: Database Design →](06-database-design.md)
