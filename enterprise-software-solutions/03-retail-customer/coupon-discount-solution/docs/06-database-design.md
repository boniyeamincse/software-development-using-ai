# 06 - Coupon Database Design

## Core Schema Components

### 1. Campaigns
- `campaign_id`, `name`, `status` (Draft/Active/Archived), `start_date`, `end_date`, `budget_limit`

### 2. Discount Rules
- `rule_id`, `campaign_id`, `type` (Percentage, Fixed, BOGO), `value`, `constraints_json` (e.g., `["min_spend": 50]`)

### 3. Discount Codes
- `code_id`, `campaign_id`, `code_string` (Indexed/Hashed), `max_redemptions`, `current_redemptions`

### 4. Redemptions (Audit Log)
- `redemption_id`, `code_id`, `order_ref`, `customer_id`, `amount_saved`, `timestamp`

## Key Relationships
- **One-to-Many**: One Campaign can have multiple Rules (Logical AND/OR).
- **One-to-Many**: One Campaign can have millions of Codes.
- **One-to-Many**: One Code can have multiple Redemptions (if multi-use).
