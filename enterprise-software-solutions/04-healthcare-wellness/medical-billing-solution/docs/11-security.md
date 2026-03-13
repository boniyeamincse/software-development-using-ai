# 11 - Medical Billing Security & Privacy

## Financial & HIPAA Integrity
- **SOC2 Type II Compliance**: Ensuring high-standard controls for financial and data security.
- **Field-Level PII Encryption**: Patient names and SSNs are encrypted at the database level.
- **Identity Redirection**: Masking sensitive clinical labels from insurance specialists unless "Need to Know" is established.

## Access & Audit
- **Strict RBAC**: Accountants can view "Taxes/Payouts" but never "Patient Clinical Diagnoses."
- **Immutable Log Vault**: Every single keystroke that modifies a claim is recorded and cannot be deleted.
- **Multi-Factor Authentication (MFA)**: Mandatory for every user login without exception.

## Infrastructure Protection
- **Vulnerability Scanning**: Weekly automated scans for dependency and cloud config vulnerabilities.
- **EDI Validation**: Ensuring no malicious code is injected into inbound 835 or 271 files.
- **Encrypted EDI Tunnels**: All transmissions to clearinghouses occur over encrypted, authenticated channels.

---
[← Previous: Technology Stack](10-tech-stack.md) | [Back to Index](README.md) | [Next: Deployment Strategy →](12-deployment.md)
