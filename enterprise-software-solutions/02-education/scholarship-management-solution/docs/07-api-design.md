# 07 - Scholarship API Design

## Applicant Interfaces
- `GET /api/v1/scholarships/search`: Filter available grants based on user profile logic.
- `POST /api/v1/applications/submit`: Multi-part upload for form data and files.
- `GET /api/v1/applications/status`: Polling for review updates.

## Management Interfaces
- `PATCH /api/v1/review/score`: Submit committee scores for an application.
- `POST /api/v1/disburse/trigger`: Execute scheduled payment to student accounts.

## Integration Endpoints
- `GET /api/v1/verify/transcript`: Query institutional SIS for grade verification.
- `POST /api/v1/notify/award`: Send formal award notification emails/PDFs.

## Security
- **OAuth Scopes**: `apply:read`, `review:write`, `funds:admin`.
- **Encryption**: Field-level encryption for tax/SSN data.

---
[← Previous: Database Design](06-database-design.md) | [Back to Index](README.md) | [Next: UI Pages →](08-ui-pages.md)
