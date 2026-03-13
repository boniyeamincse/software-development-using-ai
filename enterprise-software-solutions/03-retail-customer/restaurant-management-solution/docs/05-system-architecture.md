# 05 - Restaurant System Architecture

## High-Performance & Offline-First
The system uses a **Local-Cloud Hybrid Architecture** to ensure that the restaurant can continue to take orders and print tickets even during an internet outage.

## Technical Infrastructure
- **Frontend**: React-Native (for iOS/Android Tablets) and React (for Admin).
- **Control Tier**: An on-premise "Bridge Server" (typically a Raspberry Pi or NUC) for local printing and high-speed KDS sync.
- **Backend API**: Node.js (TypeScript) or Go for handling high-frequency order streams.
- **Print Orchestrator**: A specialized service for managing ESC/POS thermal printers over LAN.

## Data Layer
- **Relational DB (PostgreSQL)**: Storing the master source of truth for orders, inventory, and users.
- **Document DB (MongoDB)**: For storing complex, fast-changing menu structures and modifiers.
- **Distributed Cache (Redis)**: For real-time state management of the KDS and Floor map.

---
[← Previous: User Roles & Permissions](04-user-roles.md) | [Back to Index](README.md) | [Next: Database Design →](06-database-design.md)
