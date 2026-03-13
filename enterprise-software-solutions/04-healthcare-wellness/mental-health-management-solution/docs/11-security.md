# 11 - Mental Health Security & Privacy

## Extreme Patient Privacy
- **Zero-Knowledge Architecture**: Clinical notes are encrypted at the client-side (or API edge) before storage; even DB administrators cannot view therapy content.
- **Double-Masked PII**: Patient names are stored in a separate, disconnected vault from their clinical ID to prevent data reconstruction in case of a breach.
- **Field-Level Encryption**: Every DAP/SOAP note row is encrypted with its own unique IV (Initialization Vector).

## Access & Trust
- **Hardware-Based MFA**: Mandatory use of YubiKey or secure app-based codes for all clinical logins.
- **Strict Clinical Scoping**: Only the primary therapist and clinical supervisor can view a patient's full note history.
- **WORM Audit Trails**: Immutable "Read logs" that record exactly when a therapist viewed a specific patient's chart.

## Compliance
- **HIPAA/HITECH Compliance**: Strict adherence to the Privacy, Security, and Breach Notification rules.
- **Ethical AI guardrails**: Ensuring AI-assisted transcriptions are purged from temporary memory immediately after the note is finalized.
- **Right-to-be-Forgotten**: Secure, permanent data shredding policies for patients who end their care relationship.

---
[← Previous: Technology Stack](10-tech-stack.md) | [Back to Index](README.md) | [Next: Deployment Strategy →](12-deployment.md)
