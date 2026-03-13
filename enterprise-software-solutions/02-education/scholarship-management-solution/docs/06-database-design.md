# 06 - Scholarship Database Design

## Core Schema Components

### 1. Scholarship Funds
- `fund_id`, `donor_id`, `original_balance`, `current_balance`, `rules_json`

### 2. Applications
- `application_id`, `student_id`, `fund_id`, `status` (Draft/Under Review/Awarded/Rejected), `submission_timestamp`

### 3. Review Rounds
- `round_id`, `application_id`, `reviewer_id`, `score`, `comments`, `is_blind`

### 4. Disbursements
- `disbursement_id`, `application_id`, `amount`, `status` (Scheduled/Paid), `transaction_ref`

## Key Relationships
- **One-to-Many**: One Fund supports many Applications.
- **Many-to-Many**: Applications assigned to multiple Reviewers.
