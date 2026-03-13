# 05 - Subscription System Architecture

## Accuracy & Security Centric
The system is built on a **Transactional Multi-Tenant Architecture** designed to ensure 100% financial accuracy and strict data isolation.

## Technical Infrastructure
- **Frontend**: Next.js (Admin Dashboard) and React (Customer Portal).
- **Backend API**: Go (Golang) or Java (Spring Boot) for handling high-concurrency payment processing.
- **Worker Tier**: Distributed task queue (Celery or Temporal) for processing thousands of recurring charges in parallel.
- **Usage Ingestion**: High-speed stream processing (Apache Kafka or AWS Kinesis) for metered billing data.

## Data Layer
- **Relational DB (PostgreSQL)**: Storing the "Source of Truth" for ledgers, subscriptions, and plans.
- **Read-Only Analytics**: Snowflake or BigQuery for performing complex MRR/ARR calculations over millions of records.
- **Vault (PCI-Compliant)**: Tokenized storage of payment methods (e.g., Stripe/Braintree vaulting).
