# 06 - Restaurant Database Design

## Core Schema Components

### 1. Menus & Items
- `item_id`, `name`, `price`, `tax_category`, `is_modifier` (BOOLEAN)
- `recipe_id`, `item_id`, `ingredients_json` (List of SKU weights)

### 2. Orders & Checks
- `order_id`, `table_id`, `server_id`, `status` (Sent/Preparing/Closed), `payment_status`
- `order_item_id`, `order_id`, `item_id`, `modifiers_json`, `prep_status`

### 3. Inventory & Purchasing
- `sku_id`, `name`, `unit_type` (g, ml, pack), `current_stock`, `reorder_level`

### 4. Staff & Shifts
- `staff_id`, `role_id`, `hourly_rate`
- `shift_id`, `staff_id`, `clock_in`, `clock_out`

## Key Relationships
- **One-to-Many**: One Order has multiple Order Items.
- **Many-to-Many**: Items use multiple Raw Ingredients.
- **One-to-One**: One Order Item has one KDS Task mapping.

---
[← Previous: System Architecture](05-system-architecture.md) | [Back to Index](README.md) | [Next: API Design →](07-api-design.md)
