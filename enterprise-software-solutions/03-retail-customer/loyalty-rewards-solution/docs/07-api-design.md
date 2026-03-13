# 07 - Loyalty & Rewards API Design

## Customer Portal APIs
- `GET /api/v1/loyalty/balance`: Fetch real-time point count and tier status.
- `GET /api/v1/loyalty/history`: Paginated list of point earnings and burns.
- `POST /api/v1/loyalty/redeem`: Initiate a reward purchase.

## Merchant & POS APIs
- `POST /api/v1/loyalty/earn`: Log points from a successful purchase transaction.
- `POST /api/v1/loyalty/validate-redemption`: Check if a customer has enough points for a specific checkout discount.

## Admin & Rules
- `PATCH /api/v1/admin/rules/update`: Modify point multipliers or seasonal earning conditions.

## Security
- **HMAC / JWT**: Ensuring POS transactions are authenticated and untampered.
- **Idempotency Keys**: To prevent accidental double-posting of points during network retries.

---
[← Previous: Database Design](06-database-design.md) | [Back to Index](README.md) | [Next: UI Pages →](08-ui-pages.md)
