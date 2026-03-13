# 06 - Telemedicine Database Design

## Core Schema Components

### 1. Virtual Sessions & Rooms
- `session_id`, `appointment_ref_id`, `room_token`, `status` (Created/Active/Ended)
- `started_at`, `ended_at`, `media_region_id`

### 2. Participants & Identities
- `participant_id`, `session_id`, `user_id`, `role` (Provider/Patient/Translator)
- `connection_metadata_json` (Device, Browser, Peer-ID)

### 3. Patient RPM Metrics
- `metric_id`, `patient_id`, `device_id`, `timestamp`
- `type` (BP/O2/Glucose), `value`, `is_anomalous` (Alert Flag)

### 4. Messaging & Chat
- `message_id`, `session_id`, `sender_id`, `encrypted_payload`, `timestamp`
- `is_attachment`, `s3_reference`

### 5. Consents & Regulatory
- `consent_id`, `patient_id`, `session_id`, `timestamp`, `ip_address`
- `audit_event`, `user_id`, `action`, `outcome`, `timestamp`

## Key Relationships
- **One-to-One**: One Appointment links to one Virtual Session.
- **One-to-Many**: One Session can have multiple Participants.
- **One-to-Many**: One Patient has a historical stream of RPM Metrics.
- **Many-to-One**: Many logical Messages belong to one Virtual Session/Encounter.

---
[← Previous: System Architecture](05-system-architecture.md) | [Back to Index](README.md) | [Next: API Design →](07-api-design.md)
