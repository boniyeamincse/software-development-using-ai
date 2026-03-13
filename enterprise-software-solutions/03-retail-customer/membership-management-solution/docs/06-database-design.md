# 06 - Membership Database Design

## Core Schema Components

### 1. Members
- `member_id`, `name`, `email`, `phone`, `current_plan_id`, `status` (Active/Past Due/Canceled/Frozen)

### 2. Plans & Tiers
- `plan_id`, `name`, `price`, `interval` (Mo/Yr), `access_rules_json`

### 3. Subscription History
- `sub_id`, `member_id`, `start_date`, `end_date`, `auto_renew` (BOOLEAN)

### 4. Entry Logs
- `log_id`, `member_id`, `gateway_id`, `timestamp`, `result` (Success/Fail)

## Key Relationships
- **One-to-Many**: One Member has multiple Subscription records (over time).
- **Many-to-One**: Many Members on the same Plan.
- **One-to-Many**: One Member has many Entry Logs.

---
[← Previous: System Architecture](05-system-architecture.md) | [Back to Index](README.md) | [Next: API Design →](07-api-design.md)
