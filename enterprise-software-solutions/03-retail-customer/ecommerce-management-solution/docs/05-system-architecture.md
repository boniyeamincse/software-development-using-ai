# 05 - Ecommerce System Architecture

## Headless & Event-Driven
The solution uses a **Decoupled Architecture** where the commerce core is exposed via high-performance APIs.

## Tech Infrastructure
- **Micro-Frontends**: Decoupling the Product Search from the Checkout flow for independent scaling.
- **Serverless Functions**: Handling intermittent heavy tasks like "Invoice Generation" or "Email Blasts."
- **Event Bus (Redis/RabbitMQ)**: Orchestrate actions like "Notify Logistics on Order Paid."

## Data Strategy
- **Document Store (MongoDB)**: For flexible product catalogs with varying attributes.
- **Relational DB (PostgreSQL)**: To ensure data integrity for financial transactions and orders.
- **Search Cluster (Elasticsearch)**: Powering millisecond-range product filtering and searches.

---
[← Previous: User Roles & Permissions](04-user-roles.md) | [Back to Index](README.md) | [Next: Database Design →](06-database-design.md)
