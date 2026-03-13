# 06 - Mental Health Database Design

## Core Schema Components

### 1. Patients & Clinical Relationships
- `patient_id`, `name_masked`, `contact_info_encrypted`, `emergency_contact_json`
- `relationship_id`, `patient_id`, `clinician_id`, `type` (Primary/Consultant)

### 2. Clinical Notes (Encrypted Vault)
- `note_id`, `patient_id`, `clinician_id`, `type` (SOAP/DAP/Assessment)
- `content_blob_encrypted`, `encryption_key_id`, `status` (Draft/Signed)

### 3. Safety Plans & Crisis Logs
- `plan_id`, `patient_id`, `triggers_json`, `coping_skills_json`, `contacts_json`
- `alert_id`, `patient_id`, `trigger_source` (Assessment/Manual), `resolution_status`

### 4. Therapeutic Assessments
- `asmt_id`, `template_id` (PHQ9/GAD7), `patient_id`, `total_score`
- `responses_json_encrypted`, `timestamp`

### 5. Appointments & Telehealth
- `appt_id`, `patient_id`, `clinician_id`, `room_token_encrypted`, `status`
- `auth_id`, `insurance_payer_id`, `sessions_approved`, `sessions_used`

## Key Relationships
- **One-to-Many**: One Patient has many historical Clinical Notes.
- **Many-to-Many**: Patients can be part of multiple Therapy Groups.
- **One-to-One**: One High-Scoring Assessment may trigger one Priority Crisis Incident.
- **Many-to-One**: Many Appointments are governed by one Insurance Authorization.

---
[← Previous: System Architecture](05-system-architecture.md) | [Back to Index](README.md) | [Next: API Design →](07-api-design.md)
