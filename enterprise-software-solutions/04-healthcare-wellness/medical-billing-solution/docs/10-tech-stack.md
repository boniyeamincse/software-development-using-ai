# 10 - Medical Billing Technology Stack

## Core Engineering
- **Backend API**: Java (Spring Boot) or .NET Core (for strong typing and EDI throughput).
- **Frontend**: Next.js (React) for data-intensive administrative tools.
- **Workflow Engine**: Temporal or Camunda for managing long-running claim states.

## EDI & Connectivity
- **EDI Transcriber**: Edifecs or specialized X12 parser libraries.
- **Messaging**: RabbitMQ or Kafka for high-volume claim batch processing.
- **SFTP/VPN**: Dedicated secure tunnels for Clearinghouse connectivity.

## Data & Reliability
- **Primary DB**: SQL Server or AWS Aurora (PostgreSQL) with ACID compliance.
- **Reporting Store**: Snowflake or BigQuery for multi-year financial trend analysis.
- **Caching**: Redis for real-time claim scrubbing sessions.

## Deployment
- **Platform**: Enterprise Cloud (Azure/AWS) with High Availability clusters.
- **Compliance**: SOC2 Type II and HIPAA-compliant infrastructure setup.
- **Monitoring**: Datadog (for transaction tracing) and Sentry (for error capture).
