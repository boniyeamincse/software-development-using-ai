# 06 - Subscription Database Design

## Core Schema Components

### 1. Customers & Payment Methods
- `customer_id`, `email`, `currency`, `tax_id`, `payment_token` (PCI safe)

### 2. Product Catalog
- `plan_id`, `name`, `billing_interval`, `amount`, `pricing_model` (Flat/Tiered)

### 3. Subscriptions
- `sub_id`, `customer_id`, `plan_id`, `status` (Active, Trialling, Past Due), `current_period_start`, `current_period_end`

### 4. Applied Coupons
- `coupon_id`, `code`, `discount_type`, `amount_off`, `times_redeemed`

### 5. Invoices & Line Items
- `invoice_id`, `customer_id`, `total_amount`, `tax_amount`, `paid_at`
- `item_id`, `invoice_id`, `description`, `amount`

## Key Relationships
- **One-to-Many**: One Customer can have multiple Subscriptions (e.g., Add-ons).
- **One-to-Many**: One Subscription generates multiple Invoices over time.
- **Many-to-One**: Many Invoices can use one Coupon.

---
[← Previous: System Architecture](05-system-architecture.md) | [Back to Index](README.md) | [Next: API Design →](07-api-design.md)
