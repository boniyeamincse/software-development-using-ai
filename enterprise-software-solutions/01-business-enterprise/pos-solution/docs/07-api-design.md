# 07 - POS API Design

## Transactional & Sales
- `POST /api/v1/sales/checkout`: Finalize an order and trigger payment.
- `GET /api/v1/sales/history`: Retrieve recent transactions for returns.
- `POST /api/v1/shifts/close`: Reconcile cash drawer and end personal session.

## Product & Stock
- `GET /api/v1/products/sync`: Differential sync of catalog updates to the edge.
- `PATCH /api/v1/inventory/adjust`: Manual stock correction entry.

## Loyalty
- `GET /api/v1/customers/lookup`: Identify a customer and fetch reward status.

## Security & Reliability
- **Offline Tokens**: Cryptographically signed local sales that the cloud can verify later.
- **EMV Pass-Through**: Secure, encrypted communication between POS and Payment Terminal (P2PE).
- **MFA (Multi-Factor Authentication)**: Mandatory for manager-only price overrides and closures.

---
[← Previous: Database Design](06-database-design.md) | [Back to Index](README.md) | [Next: UI Pages →](08-ui-pages.md)
