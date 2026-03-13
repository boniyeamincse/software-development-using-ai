# 06 - Contract Database Design

## Core Schema Components

### 1. Contracts & Templates
- `contract_id`, `template_id`, `title`, `status` (Draft/Negotiation/Approved/Signed/Active/Expired)
- `current_version_id`, `owner_id`, `effective_date`, `expiry_date`

### 2. Parties & Entities
- `party_id`, `name`, `tax_id`, `address`, `role` (Internal/Counter-party)
- `contact_id`, `name`, `email`, `party_id`

### 3. Clauses & Playbooks
- `clause_id`, `playbook_id`, `standard_text`, `preferred_text`, `fall_back_text`

### 4. Workflow & Revisions
- `revision_id`, `contract_id`, `author_id`, `s3_path`, `change_log_json`
- `approval_id`, `contract_id`, `approver_id`, `status`, `decision_date`

### 5. Obligations
- `obligation_id`, `contract_id`, `due_date`, `frequency`, `responsible_party_id`

## Key Relationships
- **One-to-Many**: One Contract has multiple Revisions.
- **Many-to-Many**: One Contract can have multiple active Parties.
- **One-to-Many**: One Master Agreement has many Statements of Work (SOWs).

---
[← Previous: System Architecture](05-system-architecture.md) | [Back to Index](README.md) | [Next: API Design →](07-api-design.md)
