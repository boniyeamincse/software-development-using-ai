# 07 - Expense Management API Design

## Submission & Processing
- `POST /api/v1/receipts/upload`: Trigger OCR processing for a new image.
- `POST /api/v1/reports`: Create a formal expense report from a list of items.
- `GET /api/v1/policies/validate`: Real-time check of an item against company spend rules.

## Approvals & Finance
- `PATCH /api/v1/reports/:id/approve`: Move a report to the next approval stage.
- `POST /api/v1/reimbursement/batch`: Process a set of approved reports for bank transfer.

## Connectivity
- `POST /api/v1/webhooks/card-pulse`: Receive real-time transaction notifications from bank partners.

## Security
- **JWT Authentication**: Secure user access for mobile and web.
- **Signed S3 URLs**: Ensuring receipt images are only accessible to authorized approvers.
- **Idempotency**: Preventing double-submission of expense items on mobile retries.

---
[← Previous: Database Design](06-database-design.md) | [Back to Index](README.md) | [Next: UI Pages →](08-ui-pages.md)
