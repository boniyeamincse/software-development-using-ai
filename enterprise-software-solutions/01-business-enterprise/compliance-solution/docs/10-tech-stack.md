# 10 - Compliance Technology Stack

## Core Engineering
- **Backend API**: Python (Django/FastAPI) or Node.js.
- **Frontend**: Next.js (React) for data-heavy administrative interfaces.
- **Scanning Engine**: Custom wrappers for AWS Config, Azure Policy, and Terraform Compliance.

## Data & Security
- **Master Database**: PostgreSQL with row-level security for sensitive incident data.
- **Evidence Storage**: AWS S3 with Object Lock (WORM) enabled for audit-critical files.
- **Identity**: Okta or Azure AD for SAML-based attestation verification.

## Infrastructure
- **Hosting**: Sovereign Cloud regions for highly sensitive government compliance (e.g., AWS GovCloud).
- **Encryption**: Customer-Managed Keys (CMK) via KMS for all compliance-related data.
- **Logging**: Dedicated ELK/Splunk cluster for immutable audit trail capture.

---
[← Previous: System Workflows](09-workflow.md) | [Back to Index](README.md) | [Next: Security & Compliance →](11-security.md)
