# 10 - Expense Technology Stack

## Core Engineering
- **Backend API**: Node.js (TypeScript) or Go.
- **Frontend**: Next.js (Web) and React Native (Mobile).
- **OCR/AI**: AWS Textract or custom Python-based ML models.

## Data & Safety
- **Master Database**: PostgreSQL.
- **Document Store**: Encrypted AWS S3.
- **Queue/Workflow**: Temporal.io for ensuring approval sequences survive system restarts.

## Infrastructure
- **Serverless**: AWS Lambda for handling computationally heavy OCR tasks.
- **Monitoring**: Datadog (Error rates) and Sentry (Mobile crash logs).
- **Security**: Auth0 or Okta for Enterprise-grade identity management.
