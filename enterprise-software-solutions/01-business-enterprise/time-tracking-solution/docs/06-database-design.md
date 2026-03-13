# 06 - Time Database Design

## Core Schema Components

### 1. Time Entries
- `entry_id`, `user_id`, `task_id`, `project_id`, `start_time`, `end_time`, `duration_seconds`
- `status` (Draft/Submitted/Approved/Rejected), `is_billable`, `note_md`

### 2. Rates & Costs
- `rate_id`, `user_id`, `project_id`, `billable_rate`, `cost_rate`, `currency`, `effective_date`

### 3. Timesheets (Aggregates)
- `timesheet_id`, `user_id`, `period_start`, `period_end`, `total_hours`, `submission_timestamp`

### 4. Policies
- `policy_id`, `name`, `overtime_threshold_daily`, `overtime_threshold_weekly`, `break_requirement_minutes`

## Key Relationships
- **Many-to-One**: Many Time Entries belong to one Tasks.
- **Many-to-One**: Many Time Entries belong to one weekly Timesheet.
- **One-to-Many**: One User has multiple historical Rates over time.
