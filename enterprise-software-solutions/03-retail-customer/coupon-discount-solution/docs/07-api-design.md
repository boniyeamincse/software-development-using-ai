# 07 - Coupon & Discount API Design

## Evaluation & Redemption
- `POST /api/v1/evaluate`: Pass the cart object; receive total discounts and list of applicable rules.
- `POST /api/v1/redeem`: Permanently mark a code or cart-level discount as "Used" for a specific order.

## Campaign & Code Management
- `POST /api/v1/campaigns`: Create a new promotional event.
- `GET /api/v1/codes/validate/:code`: Quick check for code existence and validity (Pre-evaluation).

## Admin Analytics
- `GET /api/v1/reports/campaign-roi`: Detailed metrics for a specific promotion.

## Security
- **Rate Limiting**: Aggressive limits on the `/validate` endpoint to prevent brute-forcing of unique codes.
- **Request Signing**: Ensuring checkout systems are authorized to modify redemption counts.

---
[← Previous: Database Design](06-database-design.md) | [Back to Index](README.md) | [Next: UI Pages →](08-ui-pages.md)
