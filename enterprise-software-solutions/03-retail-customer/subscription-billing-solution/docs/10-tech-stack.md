# 10 - Subscription Technology Stack

## Core Engineering
- **Backend API**: Go (Golang) for massive parallel payment processing.
- **Frontend**: React-Next.js.
- **Task Orchestration**: Temporal.io or AWS Step Functions.

## Financial & Data
- **Primary Database**: PostgreSQL (configured for strictly serializable transactions).
- **Time-Series (Usage)**: TimescaleDB or InfluxDB.
- **Payment Gateway**: Integration with Stripe, Adyen, or Paddle.

## Infrastructure
- **Hosting**: AWS (multi-region availability).
- **Security**: AWS KMS for managing encryption keys.
- **Logging**: ELK Stack for deep audit trails.
