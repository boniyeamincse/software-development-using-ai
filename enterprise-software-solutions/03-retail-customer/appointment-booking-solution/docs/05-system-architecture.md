# 05 - Appointment Booking Architecture

## Real-Time Concensus Architecture
The system is built on an **Event-Driven Distributed Architecture** to prevent double-bookings across high-traffic environments.

## Technical Infrastructure
- **Frontend**: Next.js (Web) & Flutter (Mobile) for cross-platform booking widgets.
- **Backend API**: Node.js (Express) or Go for high-concurrency slot locking.
- **Cache (Redis)**: Used for optimistic locking to ensure no two customers book the same slot simultaneously.
- **Database (PostgreSQL)**: To maintain complex relationships between Staff, Services, and Bookings.

## Integration Layer
- **CalDav / iCal**: For external calendar synchronization.
- **Webhook Engine**: To notify downstream systems (CRM, ERP) of new bookings.
