# 05 - Coupon System Architecture

## Performance & Scalability Design
The system uses a **Fast-Path Rule Architecture** to ensure that adding complex promotions does not increase checkout latency.

## Technical Infrastructure
- **Frontend**: React-based administrative dashboard.
- **Rule Engine**: Written in Rust or Go for ultra-low latency execution.
- **State Store**: Redis (for active campaign rules and real-time usage counters).
- **Communication**: Async event bus (NATS or RabbitMQ) for updating analytics dashboards without blocking checkout.

## Data Layer
- **Relational DB (PostgreSQL)**: Storing campaign definitions and historical redemption logs.
- **Distributed Cache (Redis)**: Storing the "Hot-Set" of valid unique codes and their current usage counts.
