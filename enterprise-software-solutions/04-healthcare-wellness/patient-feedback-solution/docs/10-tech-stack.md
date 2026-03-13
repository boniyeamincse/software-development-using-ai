# 10 - Patient Feedback Technology Stack

## Core Development
- **Backend API**: Node.js (TypeScript) for high-speed event handling.
- **Frontend (Web)**: Next.js (React) for admin dashboards.
- **Frontend (Survey)**: Lightweight Preact or React optimized for mobile PWA performance.

## Intelligence & Analysis
- **NLP Engine**: Python-based microservice using specialized healthcare NLP (spaCy / Transformers).
- **Theme Discovery**: Bert-based topic modeling for automated feedback categorization.
- **Search**: Elasticsearch for multi-dimensional comment exploration.

## Communication & Serverless
- **SMS/Email**: AWS Pinpoint and Twilio for intelligent messaging delivery.
- **Cloud Layer**: AWS Lambda or Google Clouds Functions for an elastically scaling survey engine.
- **Real-Time**: AWS AppSync (GraphQL) for live dashboard score updates.

## Data & Infrastructure
- **Relational DB**: PostgreSQL (Aurora) for configuration and user master data.
- **Document DB**: MongoDB or DynamoDB for highly flexible survey responses.
- **Monitor**: Datadog for system health and custom "Survey Success Rate" metrics.

---
[← Previous: System Workflows](09-workflow.md) | [Back to Index](README.md) | [Next: Security & Compliance →](11-security.md)
