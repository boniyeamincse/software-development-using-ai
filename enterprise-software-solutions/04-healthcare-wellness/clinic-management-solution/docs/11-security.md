# 11 - Clinic Security & Data Privacy

## Compliance & Privacy
- **HIPAA Compliant Hosting**: Ensuring all data resides in encrypted, audited cloud regions.
- **Business Associate Agreement (BAA)**: Provided for all 3rd party integrations.
- **Automatic Session Timeout**: Aggressive logout policies for clinical terminals left unattended.

## Access Control
- **Role-Based Scoping**: Receptionists see "Billing/Info" but can never view "Clinical SOAP History."
- **Device Locking**: Ability for admins to revoke access for specific mobile devices (lost/stolen phones).
- **MFA**: Compulsory Multi-Factor Authentication for all clinic staff.

## Data Protection
- **AES-256 Encryption**: Every clinical word and patient ID is encrypted at rest.
- **Point-in-Time Recovery**: Database backups allow restoration to any second in the last 35 days.
- **Audit Reports**: Instant generation of "Who accessed this patient?" reports for privacy officers.

---
[← Previous: Technology Stack](10-tech-stack.md) | [Back to Index](README.md) | [Next: Deployment Strategy →](12-deployment.md)
