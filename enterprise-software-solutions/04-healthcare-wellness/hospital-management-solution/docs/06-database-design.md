# 06 - Hospital Database Design

## Core Schema Components

### 1. Patients & EHR
- `patient_id`, `mrn` (Medical Record Number), `name`, `dob`, `gender`
- `encounter_id`, `patient_id`, `admission_type`, `admission_date`, `discharge_date`
- `medical_history_json`, `allergies_list`

### 2. Clinical Observations
- `observation_id`, `encounter_id`, `observation_type` (Vitals/Lab/Symptom), `value`, `unit`
- `observation_timestamp`, `recorded_by_id`

### 3. Orders & Prescriptions
- `order_id`, `encounter_id`, `order_type` (Medication/Lab/Imaging), `priority` (Stat/Routine)
- `prescription_id`, `medication_name`, `dosage`, `frequency`, `duration`

### 4. Facility & Resource
- `ward_id`, `name`, `type` (ICU/General/Private)
- `bed_id`, `ward_id`, `status` (Available/Occupied/Cleaning/Maintenance)

### 5. Revenue Cycle
- `invoice_id`, `encounter_id`, `total_amount`, `discount`, `tax`
- `claim_id`, `invoice_id`, `payer_id`, `claim_status` (Pending/Approved/Rejected)

## Key Relationships
- **One-to-Many**: One Patient has many Clinical Encounters.
- **One-to-Many**: One Encounter has many Clinical Observations and Orders.
- **Many-to-Many**: Doctors and Patients can interact across multiple specialized Wards.
- **One-to-One**: One Bed is assigned to exactly one Patient during an active inpatient session.

---
[← Previous: System Architecture](05-system-architecture.md) | [Back to Index](README.md) | [Next: API Design →](07-api-design.md)
