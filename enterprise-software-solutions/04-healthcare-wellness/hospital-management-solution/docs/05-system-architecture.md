# 05 - Hospital System Architecture

## High-Availability Clinical Engine
The HMS uses a **Mission-Critical Microservices Architecture** designed for 99.999% uptime and sub-second response times for life-critical data.

## Technical Infrastructure
- **Frontend**: React/Next.js for the administrative portal; React Native for mobile clinical apps.
- **Backend API**: Java (Spring Boot) or C# (.NET) for robust enterprise logic and HL7/FHIR compliance.
- **Integration Layer**: Mirth Connect (NextGen Connect) for communicating with external labs and devices.
- **Imaging Bus**: DICOM-aware gateway for high-speed transfer of medical imagery.

## Data Strategy
- **Relational DB (PostgreSQL/SQL Server)**: Standard metadata, billing, and scheduling.
- **NoSQL / FHIR Data Store**: Storing semi-structured Electronic Health Records for interoperability.
- **Object Store (S3)**: High-security storage for images and document attachments.
- **Real-Time Data**: Redis for active vital-sign stream caching.

---
[← Previous: User Roles & Permissions](04-user-roles.md) | [Back to Index](README.md) | [Next: Database Design →](06-database-design.md)
