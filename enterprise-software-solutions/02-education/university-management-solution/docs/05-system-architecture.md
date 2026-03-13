# 05 - University System Architecture

## Distributed Enterprise Design
The system uses a **Global Micro-frontend Architecture** to allow different faculties (e.g., Engineering vs. Medicine) to customize their specific UI/UX needs while sharing a central data backend.

## Edge & Cloud Connectivity
- **Global CDNs**: Low-latency access to video lectures for distance learning students.
- **Hybrid Cloud**: Sensitive student records stored on-premise (if required by local law), with compute loads in the public cloud.

## Service Layer
- **GraphQL API**: Allows client-side applications to fetch exactly what they need, minimizing bandwidth for mobile users.
- **Event Bus (RabbitMQ/Kafka)**: Handles real-time events like "Course Waitlist Clearance" or "Urgent Campus Alerts."

## Intelligent Data Tier
- **Elasticsearch**: For high-speed search across thousands of courses and research papers.
- **Managed RDBMS**: High-availability clusters for core transaction data.

---
[← Previous: User Roles & Permissions](04-user-roles.md) | [Back to Index](README.md) | [Next: Database Design →](06-database-design.md)
