# 06 - Ecommerce Database Design

## Core Schema Components

### 1. Products & Variants
- `product_id`, `sku`, `title`, `description`, `price`, `vendor_id`, `category_id`
- `variant_id`, `product_id`, `attribute_name` (Size), `attribute_value` (XL)

### 2. Inventory
- `stock_id`, `product_id`, `warehouse_location`, `current_quantity`, `reserved_quantity`

### 3. Orders & Transactions
- `order_id`, `customer_id`, `total_amount`, `status` (Paid/Pending), `shipping_address`
- `transaction_id`, `order_id`, `gateway_reference`, `provider` (Stripe/PayPal)

### 4. Reviews & Ratings
- `review_id`, `product_id`, `customer_id`, `rating`, `comment`

## Key Relationships
- **Polymorphic**: Discounts can apply to "Categories," "Specific Products," or "Total Cart."
- **One-to-Many**: One Order contains many OrderLineItems.

---
[← Previous: System Architecture](05-system-architecture.md) | [Back to Index](README.md) | [Next: API Design →](07-api-design.md)
