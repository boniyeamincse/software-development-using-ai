# 05 - Project System Architecture

## Collaborative & Event-Driven Design
The system uses a **Real-Time Synchronous Architecture** to ensure that every task update is instantly reflected across all team members' screens.

## Technical Infrastructure
- **Frontend**: Next.js (React) with optimized state management (Zustand or Redux) for handling thousands of task cards.
- **Backend API**: Node.js (TypeScript) or Go for low-latency concurrent task updates.
- **Real-Time Layer**: WebSockets (Socket.io or AWS AppSync) for instant collaboration and notification delivery.
- **Gantt Engine**: High-performance canvas-based rendering for complex project timelines.

## Data Layer
- **Relational DB (PostgreSQL)**: Storing core project, task, and user entities with complex relational integrity.
- **Cache Store (Redis)**: Storing transient real-time states and active notification queues.
- **Search (Elasticsearch)**: Enabling sub-second search across all task descriptions, comments, and files.
- **Object Storage (S3)**: For massive file storage and image assets.

---
[← Previous: User Roles & Permissions](04-user-roles.md) | [Back to Index](README.md) | [Next: Database Design →](06-database-design.md)
