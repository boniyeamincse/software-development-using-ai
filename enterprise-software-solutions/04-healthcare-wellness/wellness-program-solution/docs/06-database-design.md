# 06 - Wellness Database Design

## Core Schema Components

### 1. Users & Corporate Groups
- `user_id`, `corporate_id`, `department_id`, `name`, `enrollment_date`
- `corporate_id`, `name`, `plan_tier`, `sector`

### 2. Challenges & Leaderboards
- `challenge_id`, `type` (Steps/Sleep/H2O), `start_date`, `end_date`, `goal_value`
- `entry_id`, `challenge_id`, `user_id`, `current_value`, `rank`

### 3. Wearable Ingestion (Time-Series)
- `ingestion_id`, `user_id`, `metric_type`, `value`, `timestamp`, `source_device`

### 4. Health Assessments (HRA)
- `assessment_id`, `user_id`, `timestamp`, `risk_score`, `data_json` (Encrypted)

### 5. Rewards & Points
- `transaction_id`, `user_id`, `points`, `reason_code` (Challenge Won/HRA Done), `timestamp`
- `reward_id`, `name`, `point_cost`, `availability`

## Key Relationships
- **One-to-Many**: One Corporate Group has many Employees/Users.
- **Many-to-Many**: Users can participate in multiple concurrent Challenges.
- **One-to-Many**: One User has a continuous stream of Wearable Ingestion points.
- **One-to-Many**: One User has multiple historical Health Assessments.

---
[← Previous: System Architecture](05-system-architecture.md) | [Back to Index](README.md) | [Next: API Design →](07-api-design.md)
