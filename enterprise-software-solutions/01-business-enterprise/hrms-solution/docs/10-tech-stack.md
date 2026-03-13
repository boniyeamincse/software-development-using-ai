# 10 - HRMS Technology Stack

## Core Engineering
- **Backend API**: Node.js (TypeScript) or Python (FastAPI).
- **Frontend**: React-Next.js with custom UI components for data-heavy views.
- **Workflow**: Temporal.io for ensuring approval sequences never get "lost."

## Data & Safety
- **Master Database**: PostgreSQL (with Encrypted Fields for salaries/SSNs).
- **Document Storage**: Secure AWS S3 buckets.
- **Cache**: Redis for session management and quick-view dashboards.

## Infrastructure
- **Hosting**: Cloud-Managed (AWS/Azure) with VPC (Virtual Private Cloud) isolation.
- **Auth**: Okta or Azure AD (Active Directory) for SSO (Single Sign-On).
- **E-Signature**: DocuSign or HelloSign API.

---
[← Previous: System Workflows](09-workflow.md) | [Back to Index](README.md) | [Next: Security & Compliance →](11-security.md)
