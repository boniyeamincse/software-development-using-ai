# 10 - Loyalty Technology Stack

## Core Engineering
- **Backend API**: Node.js or Java (Spring Boot).
- **Frontend**: React (Admins) & Next.js (Consumers).
- **Rule Engine Engine**: JSON Rules Engine or Drools.

## Specialized Data
- **Primary Database**: PostgreSQL (for ACID compliance on points).
- **Distributed Lock**: Redis (to prevent concurrent spend issues).
- **Reporting**: BigQuery or Snowflake (for massive historical datasets).

## Infrastructure
- **Hosting**: AWS or Google Cloud.
- **Messaging**: RabbitMQ or AWS SQS.
- **Monitoring**: Datadog (Transactional tracking) and New Relic.

---
[← Previous: System Workflows](09-workflow.md) | [Back to Index](README.md) | [Next: Security & Compliance →](11-security.md)
