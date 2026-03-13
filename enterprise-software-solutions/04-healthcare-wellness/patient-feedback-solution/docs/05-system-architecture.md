# 05 - Patient Feedback System Architecture

## Event-Driven Feedback Architecture
The Patient Feedback Solution utilizes a **Serverless Event-Driven Design** to ensure that data flows from a patient's phone to a manager's dashboard in under 5 seconds.

## Technical Infrastructure
- **Frontend**: Next.js (Web) for dashboards and specialized mobile-optimized React (PWA) for patient surveys.
- **Backend API**: Node.js (TypeScript) running on AWS Lambda or Google Functions.
- **NLP Service**: Python-based microservice utilizing specialized medical sentiment models (e.g., BioGPT or custom spaCy).
- **Communication**: AWS SNS for immediate SMS triggering and Pinpoint for large-scale email campaigns.

## Data Strategy
- **Relational DB (PostgreSQL)**: Managing master data (Facilities, Departments, Staff) and survey logic.
- **NoSQL (MongoDB / DynamoDB)**: Storing the flexible, high-volume survey response documents.
- **Search Layer**: Elasticsearch for sub-second keyword and theme discovery across millions of comments.
- **Cache Layer**: Redis for real-time facility-level NPS score calculation.
