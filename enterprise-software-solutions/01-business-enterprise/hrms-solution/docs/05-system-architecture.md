# 05 - HRMS System Architecture

## Privacy-Centric & Scalable Design
The HRMS utilizes a **Microservices-Based Architecture** with enhanced security layers to handle sensitive employee PII (Personally Identifiable Information).

## Technical Infrastructure
- **Frontend**: Next.js (React) for a responsive and intuitive user experience.
- **Backend API**: Node.js (TypeScript) or Python (Django) for rapid development and secure handling of logic.
- **Workflow Engine**: Temporal.io or Camunda for complex multi-step approvals (e.g., Leave Approval -> Manager -> HR).
- **Communication Gateway**: SendGrid for internal notifications and DocuSign for contract e-signatures.

## Data Layer
- **Encryption-at-Rest Database (PostgreSQL)**: Storing core employee records with transparent data encryption.
- **NoSQL Store (MongoDB)**: For storing flexible documents and activity logs that don't fit into relational schemas.
- **Secure File Storage (Managed S3)**: For non-db assets like signed contracts and ID scans, featuring strict object-level permissions.
