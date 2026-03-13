# 10 - Mental Health Technology Stack

## Core Engineering
- **Backend API**: Go (Golang) or Rust for high-security, memory-safe clinical processing.
- **Frontend (Clinician)**: Next.js (React) for data-heavy, privacy-focused workflows.
- **Frontend (Patient)**: React Native for a secure, resilient mobile experience.

## Privacy & Encryption
- **Key Management**: HashiCorp Vault or AWS KMS for managing field-level encryption keys.
- **Encryption Engine**: Tink (by Google) or custom NaCl/libsodium for note-level crypto.
- **PDF Generation**: Secure rendering engine for healthcare superbills and charts.

## Communication & Serverless
- **Secure Video**: Jitsi or Twilio Video with peer-to-peer encryption mode.
- **Alerting**: PagerDuty or AWS SNS for high-priority crisis notifications.
- **API Defense**: Cloudflare for HIPAA-compliant WAF and DDoS protection.

## Data & Infrastructure
- **Primary DB**: PostgreSQL (Aurora) with encryption-at-rest.
- **Vault Store**: Encrypted NoSQL (MongoDB) for flexible clinical records.
- **Audit Logging**: Amazon CloudWatch Logs with immutable retention policies.

## Deployment
- **Compliance**: SOC2 Type II, HIPAA (HITECH), and GDPR-compliant cloud regions.
- **Observability**: Datadog for encrypted transaction tracing and system performance.

---
[← Previous: System Workflows](09-workflow.md) | [Back to Index](README.md) | [Next: Security & Compliance →](11-security.md)
