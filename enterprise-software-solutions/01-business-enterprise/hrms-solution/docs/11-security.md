# 11 - HRMS Security & Compliance

## Data Protection (PII)
- **Field-Level Encryption**: Sensitive data like Social Security Numbers and payroll details are encrypted before being written to the database.
- **PII Masking**: UI automatically masks sensitive fields (e.g., `***-**-6789`) unless the user has elevated "Finance" or "Admin" roles.

## Compliance & Audit
- **GDPR / CCPA Adherence**: Automated "Right to Access" and "Right to Erasure" (with legal-hold exceptions).
- **Audit Logging**: Immutable record of WHO accessed WHIC employee file and WHAT they changed.

## Access Control
- **SSO Integration**: Employees use corporate credentials to login (SAML/OpenID).
- **Granular RBAC**: Distinguishing between "Direct Manager" access vs. "General HR" access.
- **Geofencing**: Optionally restricting HR-admin access to specific corporate IP ranges.

---
[← Previous: Technology Stack](10-tech-stack.md) | [Back to Index](README.md) | [Next: Deployment Strategy →](12-deployment.md)
