# 10 - Hospital Technology Stack

## Backend & Interoperability
- **Primary API**: Java (Spring Boot) or .NET Core.
- **Compliance Engine**: Mirth Connect (for HL7 v2 and FHIR translation).
- **Communication Protocols**: TCP/IP (for device integration) and gRPC for high-speed internal service sync.

## Frontend & Clinical Apps
- **Web Interface**: React with Material UI (for high-density data layouts).
- **Mobile Apps**: React Native (Android/iOS) for physician "Ward Rounds" and trauma notifications.
- **Kiosk Interface**: Electron (Chromium-based) for patient check-in terminals.

## Data & Persistence
- **Transactional DB**: PostgreSQL with Always-On Availability clusters.
- **Imaging Storage**: AWS S3 with Glacier for long-term legal archival (7-25 years).
- **In-Memory**: Redis for live vital-sign streaming and notification queues.

## Infrastructure & Resilience
- **Platform**: Multi-zone AWS or Hybrid-Cloud (on-premise local cache for ER continuity).
- **Connectivity**: SD-WAN with redundant 5G/Satellite backup for hospital-wide internet.
- **Monitoring**: Datadog (Application health) + specialized Medical Network monitoring (ICMP/SNMP for devices).
