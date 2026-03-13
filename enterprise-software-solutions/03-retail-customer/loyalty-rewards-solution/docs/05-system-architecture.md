# 05 - Loyalty System Architecture

## High-Consistency & Real-Time Design
The system uses a **Distributed Transactional Architecture** to ensure that points are never "double-spent" and balances are always accurate across all regions.

## Technical Infrastructure
- **Frontend**: React/Next.js for the customer portal; Flutter for the mobile loyalty card.
- **Backend API**: Node.js or Java (Quarkus) for managing high-frequency point updates.
- **Rule Engine**: A custom Drools or script-based engine for evaluating complex earning conditions.
- **Event Bus**: Redis Streams or RabbitMQ for notifying other systems (Email/SMS) of point changes.

## Data Tier
- **Relational DB (PostgreSQL)**: To maintain the "Source of Truth" for point ledgers and user tiers.
- **Write-Through Cache**: To ensure sub-millisecond point-balance lookups at the POS.

---
[← Previous: User Roles & Permissions](04-user-roles.md) | [Back to Index](README.md) | [Next: Database Design →](06-database-design.md)
