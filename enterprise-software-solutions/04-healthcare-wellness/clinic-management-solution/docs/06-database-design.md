# 06 - Clinic Database Design

## Core Schema Components

### 1. Patient Identities
- `patient_id`, `external_ref`, `name`, `contact_info_json`, `insurance_policy_id`

### 2. Appointment & Scheduling
- `appointment_id`, `patient_id`, `provider_id`, `start_time`, `duration`, `status` (Booked/Arrived/Consulting/Completed/No-Show)
- `room_id`, `reason_for_visit`

### 3. Encounters & SOAP Notes
- `encounter_id`, `appointment_id`, `subjective_txt`, `objective_txt`, `assessment_txt`, `plan_txt`
- `icd10_codes_json`, `cpt_codes_json`

### 4. Prescriptions & Orders
- `rx_id`, `encounter_id`, `medication_id`, `dosage`, `sig_instruction`, `pharmacy_ref_id`

### 5. Billing & LEDGER
- `bill_id`, `encounter_id`, `total_amount`, `paid_amount`, `insurance_covered`, `balance`
- `transaction_id`, `bill_id`, `payment_method`, `timestamp`

## Key Relationships
- **One-to-Many**: One Patient has multiple Appointments and Encounters.
- **Many-to-One**: Many Appointments link to one Doctor/Provider.
- **One-to-One**: One Encounter usually has one associated Bill (in a clinic setting).

---
[← Previous: System Architecture](05-system-architecture.md) | [Back to Index](README.md) | [Next: API Design →](07-api-design.md)
