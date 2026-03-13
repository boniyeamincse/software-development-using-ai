# 06 - CRM Database Design

## Core Schema Components

### 1. Accounts & Contacts
- `account_id`, `company_name`, `industry`, `annual_revenue`, `website`
- `contact_id`, `account_id`, `first_name`, `last_name`, `email`, `phone`, `job_title`

### 2. Leads & Opportunities
- `lead_id`, `source`, `status` (New/Attempted/Qualified/Disqualified)
- `opportunity_id`, `contact_id`, `account_id`, `stage_id`, `value`, `close_date`

### 3. Activities & Tasks
- `activity_id`, `type` (Call/Email/Meeting), `subject`, `duration`, `outcome`, `recorded_url`
- `task_id`, `assigned_to`, `due_date`, `priority`, `status`

### 4. Pipelines & Stages
- `pipeline_id`, `name`
- `stage_id`, `pipeline_id`, `probability`, `order_sequence`

## Key Relationships
- **One-to-Many**: One Account has multiple Contacts.
- **One-to-Many**: One Account has multiple Opportunities.
- **Many-to-One**: Many Activities linked to one Opportunity or Contact.

---
[← Previous: System Architecture](05-system-architecture.md) | [Back to Index](README.md) | [Next: API Design →](07-api-design.md)
