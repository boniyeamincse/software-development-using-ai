# 06 - POS Database Design

## Core Schema Components

### 1. Sales & Orders
- `sales_id`, `store_id`, `register_id`, `cashier_id`, `timestamp`
- `status` (Completed/Voided/Returned), `total_amount`, `tax_total`, `payment_method`

### 2. Line Items (Items Sold)
- `item_id`, `sales_id`, `product_id`, `quantity`, `unit_price`, `discount_applied`

### 3. Products & Inventory
- `product_id`, `sku`, `name`, `category_id`, `price`, `cost`
- `inventory_id`, `store_id`, `product_id`, `stock_quantity`, `reorder_level`

### 4. Shifts & Cash Management
- `shift_id`, `user_id`, `start_time`, `end_time`, `expected_cash`, `actual_cash`

### 5. Loyalty & CRM
- `customer_id`, `phone`, `email`, `point_balance`, `last_purchase`

## Key Relationships
- **One-to-Many**: One Sale has multiple Line Items.
- **One-to-Many**: One Store has many Registers and Shifts.
- **Many-to-Many**: Products can belong to multiple Stores with different stock levels.

---
[← Previous: System Architecture](05-system-architecture.md) | [Back to Index](README.md) | [Next: API Design →](07-api-design.md)
