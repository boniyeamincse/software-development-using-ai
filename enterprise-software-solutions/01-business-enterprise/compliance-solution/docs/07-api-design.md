# 07 - Compliance API Design

## Framework & Requirements
- `GET /api/v1/frameworks`: Retrieve the library of active compliance standards.
- `GET /api/v1/health/overall`: Fetch the current real-time compliance score for the enterprise.

## Evidence & Automated Monitoring
- `POST /api/v1/evidence/collect`: Manual trigger for an automated evidence gathering job.
- `POST /api/v1/scanners/callback`: Inbound endpoint for external security tools to report on control status.

## Personnel & Training
- `POST /api/v1/attestation/sign`: Record a user's digital signature on a specific policy version.

## Security
- **Strict Role-Based Scoping**: Auditors have strictly Read-Only access to specific `evidence_id` buckets.
- **HMAC Verification**: For all incoming signals from infrastructure monitoring tools.
- **Audit-Trail Logging**: Every API call within the compliance module is itself a logged compliance event.

---
[← Previous: Database Design](06-database-design.md) | [Back to Index](README.md) | [Next: UI Pages →](08-ui-pages.md)
