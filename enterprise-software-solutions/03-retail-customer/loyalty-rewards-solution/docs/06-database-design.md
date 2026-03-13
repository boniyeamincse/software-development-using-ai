# 06 - Loyalty Database Design

## Core Schema Components

### 1. Customers & Wallets
- `customer_id`, `loyalty_tier_id`, `total_points_balance`, `lifetime_points`, `join_date`

### 2. Point Ledger (The Ledger)
- `transaction_id`, `customer_id`, `amount` (Positive or Negative), `type` (Earned/Spent/Expired), `reason_ref`, `timestamp`

### 3. Tiers & Perks
- `tier_id`, `name`, `min_spend_limit`, `point_multiplier`, `perks_json`

### 4. Rewards & Redemptions
- `reward_id`, `title`, `point_cost`, `inventory_count`, `valid_until`
- `redemption_id`, `customer_id`, `reward_id`, `status` (Fulfilled/Pending)

## Key Relationships
- **One-to-Many**: One Customer has many Ledger entries.
- **Many-to-One**: Many Customers belong to one Tier.
- **One-to-Many**: One Reward can have many Redemption records.
