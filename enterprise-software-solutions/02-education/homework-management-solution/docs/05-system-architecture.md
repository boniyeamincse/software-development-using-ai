# 05 - Homework System Architecture

## Cloud-First Design
The system uses a **Serverless-Heavy Architecture** to handle the high-volume upload traffic that typically occurs right before school deadlines.

## Infrastructure Stack
- **Frontend**: React (Web) & Flutter (Mobile) for cross-platform availability.
- **Backend**: Node.js/TypeScript on AWS Lambda for auto-scaling.
- **File Processing**: AWS S3 with Lambda triggers for PDF compression and virus scanning.
- **Real-time Sync**: WebSockets for live status updates in the Teacher Dashboard.

## Storage Layer
- **NoSQL (DynamoDB)**: For flexible, high-speed metadata tracking (submission times, status).
- **Relational DB (PostgreSQL)**: To maintain the rigid hierarchy of Schools > Classes > Students.

---
[← Previous: User Roles & Permissions](04-user-roles.md) | [Back to Index](README.md) | [Next: Database Design →](06-database-design.md)
