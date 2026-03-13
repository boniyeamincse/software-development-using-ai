# 07 - Subscription API Design

## Subscription Lifecycle
- `POST /api/v1/subscriptions`: Create a new subscription for a customer.
- `PATCH /api/v1/subscriptions/:id`: Upgrade, downgrade, or cancel a subscription.
- `GET /api/v1/customers/:id/invoices`: Fetch invoice history for the portal.

## Usage Ingestion (Metered)
- `POST /api/v1/usage/log`: Send usage events for consumption-based plans.
- `GET /api/v1/usage/estimate`: Calculate currently accrued costs for the mid-billing cycle.

## Webhooks
- `POST /webhook/payment-success`: Receive notifications from the payment gateway to update subscription state.
- `POST /webhook/payment-failed`: Trigger dunning workflows and customer alerts.

## Security
- **Idempotency**: Using `Idempotency-Key` headers to prevent double-charging on API retries.
- **Key Rotation**: Automated rotation of API keys used for usage reporting.

---
[← Previous: Database Design](06-database-design.md) | [Back to Index](README.md) | [Next: UI Pages →](08-ui-pages.md)
