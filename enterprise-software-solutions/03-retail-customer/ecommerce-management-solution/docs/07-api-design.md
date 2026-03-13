# 07 - Ecommerce API Design

## Storefront (Public API)
- `GET /api/v1/products`: Search and filter products with pagination.
- `POST /api/v1/cart/add`: Add items to session-persisted cart.
- `POST /api/v1/checkout/intent`: Initiate payment and lock inventory.

## Admin & Operations
- `PATCH /api/v1/inventory/update`: Sync stock levels from warehouse ERP.
- `GET /api/v1/orders/export`: Generate daily sales report.

## Integration Standards
- **Webhooks**: Real-time notifications for "Order Payment Success" to logistics.
- **REST / GraphQL**: Dual support for varying client requirements.

---
[← Previous: Database Design](06-database-design.md) | [Back to Index](README.md) | [Next: UI Pages →](08-ui-pages.md)
