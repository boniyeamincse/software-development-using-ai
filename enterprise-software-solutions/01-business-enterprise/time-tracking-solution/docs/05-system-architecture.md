# 05 - Time System Architecture

## Accuracy & High-Concurrency Design
The system uses a **Stateful Tracking Architecture** to ensure that active timers are never lost, even during network interruptions.

## Technical Infrastructure
- **Frontend**: Next.js (React) for the web portal and React Native or Flutter for Mobile.
- **Backend API**: Node.js or Go for handling thousands of simultaneous "Pulse" updates from active timers.
- **Real-Time Data**: Redis for storing the current state of active timers before they are committed to the main database.
- **Desktop Client**: Electron for cross-platform background activity monitoring.

## Data Strategy
- **Relational DB (PostgreSQL)**: The source of truth for all "Committed" and "Approved" time logs.
- **In-Memory Store (Redis)**: Managing active "Running" timers and session data.
- **Time-Series DB (Optional)**: For high-frequency activity mapping (active vs. idle).

---
[← Previous: User Roles & Permissions](04-user-roles.md) | [Back to Index](README.md) | [Next: Database Design →](06-database-design.md)
