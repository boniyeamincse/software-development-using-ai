# 05 - Telemedicine System Architecture

## Distributed Edge & Media Design
The Telemedicine Solution utilizes a **Geographically Distributed Media Architecture** to ensure sub-100ms latency for clinical interactions globally.

## Technical Infrastructure
- **Media Engine**: WebRTC with Selective Forwarding Units (SFU) for multi-party stability.
- **Backend API**: Node.js (TypeScript) or Go for high-concurrency signaling and session management.
- **Real-Time Layer**: Redis Pub/Sub for signaling, chat synchronization, and waiting room events.
- **EHR Integration**: FHIR-based middleware for synchronizing visit data with central hospital systems.

## Data Strategy
- **Relational DB (PostgreSQL)**: Managing identities, appointments, and billing metadata.
- **NoSQL (Elasticsearch)**: Searchable chat history and clinical audit logs.
- **Media Store (S3)**: Temporary, encrypted storage for file transfers (e.g., dermatology photos).
- **Time-Series DB (InfluxDB)**: High-resolution storage for RPM vital signals (heart rate, SpO2).

---
[← Previous: User Roles & Permissions](04-user-roles.md) | [Back to Index](README.md) | [Next: Database Design →](06-database-design.md)
