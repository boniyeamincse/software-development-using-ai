# 07 - Contract Management API Design

## Document & Workflow
- `POST /api/v1/contracts`: Generate a new contract from a template.
- `PATCH /api/v1/contracts/:id/check-in`: Upload a new redlined version.
- `POST /api/v1/contracts/:id/sign`: Initiate the e-signature workflow.

## AI & Analysis
- `GET /api/v1/contracts/:id/analyze`: Trigger AI extraction of parties and dates.
- `GET /api/v1/search/semantic`: Search for "Limitation of Liability" across all active contracts.

## Repository & Admin
- `GET /api/v1/repository/renewal-report`: Fetch all contracts expiring in the next 90 days.

## Security
- **Strict JWT Scoping**: External counter-parties can only access documents explicitly shared with them.
- **Audit Logging**: Every "View," "Download," and "Revision" is logged with IP and User metadata.
- **Encryption**: Field-level encryption for highly sensitive contract values and party data.
