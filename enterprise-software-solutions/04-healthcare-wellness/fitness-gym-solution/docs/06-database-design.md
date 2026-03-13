# 06 - Fitness & Gym Database Design

## Core Schema Components

### 1. Members & Contracts
- `member_id`, `name`, `email`, `active_tier_id`, `status` (Active/Frozen/Canceled/Pending)
- `contract_id`, `member_id`, `start_date`, `end_date`, `payment_method_ref`

### 2. Check-ins & Access logs
- `log_id`, `member_id`, `branch_id`, `timestamp`, `method` (QR/RFID)
- `entry_outcome` (Allowed/Denied), `denial_reason`

### 3. Classes & Bookings
- `class_id`, `name`, `instructor_id`, `start_time`, `max_capacity`, `room_id`
- `booking_id`, `class_id`, `member_id`, `status` (Booked/Waitlist/Attended/No-Show)

### 4. Workouts & Progress
- `plan_id`, `member_id`, `trainer_id`, `data_json` (Exercises, Sets, Reps)
- `stat_id`, `member_id`, `metric_type` (Weight/Body Fat), `value`, `timestamp`

### 5. Pro-Shop & Transactions
- `product_id`, `name`, `stock_quantity`, `price`
- `order_id`, `member_id`, `total_amount`, `payment_status`

## Key Relationships
- **One-to-Many**: One Member can have multiple Contracts (History).
- **One-to-Many**: One Member has a continuous stream of Check-in Logs.
- **Many-to-Many**: Members can book many Classes; Classes have many Members.
- **One-to-Many**: One Trainer manages many personal training Client plans.
