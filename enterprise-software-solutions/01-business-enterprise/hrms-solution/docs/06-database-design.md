# 06 - HRMS Database Design

## Core Schema Components

### 1. Employees & Org Structure
- `employee_id`, `first_name`, `last_name`, `email`, `joining_date`, `status` (Active/Onboarding/Exited)
- `department_id`, `name`, `manager_id`
- `job_profile_id`, `title`, `pay_grade`, `is_exempt`

### 2. Leave & Attendance
- `leave_request_id`, `employee_id`, `type`, `start_date`, `end_date`, `status` (Pending/Approved/Rejected)
- `leave_balance_id`, `employee_id`, `leave_type`, `total_accrued`, `total_used`
- `attendance_log_id`, `employee_id`, `clock_in`, `clock_out`, `location_ip`

### 3. Payroll & Benefits
- `payroll_period_id`, `start_date`, `end_date`, `status` (Open/Processing/Closed)
- `payslip_entry_id`, `employee_id`, `base_pay`, `bonuses`, `deductions`, `net_pay`

### 4. Performance
- `review_cycle_id`, `name`, `period`
- `feedback_entry_id`, `reviewer_id`, `reviewee_id`, `rating`, `comments`

## Key Relationships
- **One-to-Many**: One Employee has multiple Leave Requests.
- **One-to-Many**: One Employee has multiple Payslips over time.
- **Self-Referential**: Managers are also Employees (`manager_id` links to `employee_id`).
