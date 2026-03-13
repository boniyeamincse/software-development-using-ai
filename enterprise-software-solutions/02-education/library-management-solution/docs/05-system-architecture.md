# 05 - Library System Architecture

## Integrated & Scalable Design
The system uses a **Hybrid Cloud Architecture** to support both global digital access and local physical hardware integrations (RFID).

## Technical Infrastructure
- **Frontend**: React-based portal for students and librarians.
- **Backend**: Python (Django) for robust data management and MARC integration.
- **Search Backbone**: Elasticsearch for sub-second catalog searching across millions of records.
- **Hardware Bridge**: IoT-Gateway for real-time RFID/Barcode scanner communication.

## Asset Tier
- **Object Storage (S3)**: For digital manuscripts and e-books with version control.
- **Distributed Cache (Redis)**: For high-speed session management at the circulation desk.

---
[← Previous: User Roles & Permissions](04-user-roles.md) | [Back to Index](README.md) | [Next: Database Design →](06-database-design.md)
