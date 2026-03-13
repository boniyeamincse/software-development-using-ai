# 06 - ERP Database Design

## Core Schema Components

### 1. Finance & Ledger
- `ledger_entry_id`, `account_id`, `amount`, `debit_credit`, `transaction_date`, `status`
- `chart_of_accounts`, `account_code`, `category`, `description`

### 2. Supply Chain & Inventory
- `sku_id`, `warehouse_id`, `quantity_on_hand`, `reorder_point`, `uom` (Unit of Measure)
- `purchase_order_id`, `vendor_id`, `total_amount`, `current_status`

### 3. Manufacturing
- `bom_id`, `product_sku_id`, `parent_bom_id`
- `production_order_id`, `scheduled_date`, `assigned_line`, `status`

### 4. Sales Orders
- `sales_order_id`, `customer_ref`, `order_date`, `total_val`, `shipment_status`

## Key Relationships
- **One-to-Many**: One Ledger Entry can contain multiple line items.
- **Many-to-Many**: Products are composed of multiple raw materials (BOM).
- **One-to-Many**: One Purchase Order can contain multiple items from a vendor.
