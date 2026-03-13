# 05 - Customer Support Architecture

## Scalable & Resilient Design
The system uses a **Stateless Microservices Architecture** coupled with a robust event-bus for real-time notification delivery.

## Technical Infrastructure
- **Frontend**: Next.js for the Help Center and a heavy React/Redux SPA for the Agent Workspace.
- **API Layer**: Java (Spring Boot) or Node.js for managing complex business rules and integrations.
- **Messaging Pipeline**: Apache Kafka or RabbitMQ to ensure no message is lost during channel ingestion.
- **Search Cluster**: Elasticsearch powers the lightning-fast knowledge base and ticket searches.

## Data Tier
- **Relational DB (PostgreSQL)**: To maintain ticket state, customer relationships, and audit logs.
- **NoSQL (Redis)**: For real-time session management and agent presence tracking.
