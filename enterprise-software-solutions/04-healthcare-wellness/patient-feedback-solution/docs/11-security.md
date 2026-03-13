# 11 - Patient Feedback Security & Privacy

## Trust & Data Safety
- **True Anonymity Architecture**: A "Hard Break" in the database between feedback content and patient PII for surveys marked anonymous.
- **PHI Masking**: NLP engine automatically redacts Social Security numbers or phone numbers from open-ended comments before analysis.
- **Encryption at Rest**: AES-256 GCM for every survey response document.

## Platform Integrity
- **Anti-Spam Controls**: Rate-limiting and "Single-Link" tokens to prevent multiple submissions from the same device (unless authorized).
- **IP Reputation Scoring**: Automatic blocking of known malicious proxy or botnet IPs.
- **Secure Link Delivery**: All survey URLs delivered over HTTPS/TLS 1.3 only.

## Compliance
- **HIPAA/GDPR Compliance**: Ensuring the platform meets the highest standards for patient privacy and health data sovereignty.
- **Staff Access Logging**: Immutable audit logs showing exactly who viewed which piece of feedback (and why).
- **Compliance Reporting**: Standardized exports for regulatory quality audits and benchmark verification.

---
[← Previous: Technology Stack](10-tech-stack.md) | [Back to Index](README.md) | [Next: Deployment Strategy →](12-deployment.md)
