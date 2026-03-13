# 10 - Telemedicine Technology Stack

## Core Engineering
- **Media Framework**: WebRTC (with Mediasoup or Twilio Video).
- **Backend API**: Node.js (TypeScript) or Go for high-speed signaling.
- **Frontend**: Next.js (Web) and Flutter (iOS/Android).

## Communication & Real-time
- **Signaling**: WebSockets (Socket.io) or MQTT.
- **Messaging**: SendBird or custom E2EE XMPP/Signal-protocol wrapper.
- **RPM Ingestion**: AWS IoT Core for medical device connectivity.

## Data & Storage
- **Primary DB**: PostgreSQL (Relational).
- **Metric Store**: InfluxDB or TimescaleDB for vital sign trends.
- **Security**: HashiCorp Vault for credential and encryption key management.

## Infrastructure
- **Hosting**: AWS Multi-Region (to ensure global low-latency media relays).
- **Monitoring**: Datadog (Media metrics: Bitrate, Packet Loss, Jitter).
- **Compliance**: HIPAA-compliant BAA with all cloud providers.

---
[← Previous: System Workflows](09-workflow.md) | [Back to Index](README.md) | [Next: Security & Compliance →](11-security.md)
