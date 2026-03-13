# 06 - Medical Billing Database Design

## Core Schema Components

### 1. Payers & Contracts
- `payer_id`, `payer_name`, `tax_id`, `clearinghouse_id`, `claim_submission_format`
- `contract_id`, `payer_id`, `cpt_code`, `negotiated_rate`, `effective_date`

### 2. Claims & Line Items
- `claim_id`, `patient_id`, `provider_id`, `status` (Draft/Scrubbing/Submitted/Adjudicated/Paid/Denied)
- `line_item_id`, `claim_id`, `cpt_code`, `icd10_codes_json`, `charge_amount`, `units`

### 3. Claim Lifecycle (Audit)
- `audit_id`, `claim_id`, `action`, `user_id`, `timestamp`, `raw_edi_link`

### 4. Payments & Remittances
- `remittance_id`, `payer_id`, `check_number`, `total_amount`, `posted_status`
- `transaction_id`, `line_item_id`, `amount`, `adjustment_reason_code`, `timestamp`

### 5. Patient Financials
- `statement_id`, `patient_id`, `unpaid_balance`, `due_date`, `status`
- `payment_id`, `patient_id`, `payment_method`, `amount`, `reconciled_bill_id`

## Key Relationships
- **One-to-Many**: One Claim can have multiple Line Items (procedural codes).
- **One-to-Many**: One Claim has a detailed historical Audit Trail.
- **Many-to-One**: Many Claims are grouped into one EDI Batch for submission.
- **One-to-One**: One 835 Remittance detail ideally matches one 837 Claim line-item.

---
[← Previous: System Architecture](05-system-architecture.md) | [Back to Index](README.md) | [Next: API Design →](07-api-design.md)
