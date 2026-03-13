# 11 - Yoga Studio Security & Privacy

## Student Tranquility & Data Safety
- **Personal Information Masking**: Front-desk staff only see relevant medical flags (e.g., "Injury: Left Wrist") and ignore home addresses or phone numbers.
- **Encrypted Student Documents**: Signed waivers and health history are stored with AES-256 GCM encryption.
- **Zero-Storage Credit Policy**: No raw financial data is ever stored on studio servers; all payments utilize secure tokenization via Stripe.

## Access & Trust
- **Role-Based Access (RBAC)**: Individual teachers can only see rosters for their own classes—not the total revenue of the studio.
- **Secure Messaging**: Student-teacher communication is encrypted and stored for professional accountability.
- **MFA (Multi-Factor Auth)**: Mandatory for any accounts with access to studio-wide financials and teacher payroll.

## Compliance
- **PCI-DSS Compliance**: Ensuring global standards for secure credit card processing into the boutique retail and pass engines.
- **Right-to-be-Forgotten**: One-click data deletion for students who leave the community, ensuring adherence to GDPR/CCPA.
- **Audit Logs**: Transparent logging of which staff member modified which student account.

---
[← Previous: Technology Stack](10-tech-stack.md) | [Back to Index](README.md) | [Next: Deployment Strategy →](12-deployment.md)
