# Hostel Management Solution - Database Design

## 🗄️ Database Overview

The system uses PostgreSQL as the primary database with 50+ tables organized into logical groups.

---

## Core Tables

### Room Management Tables

**rooms**
- room_id (PK)
- room_number
- room_type_id (FK)
- floor_number
- capacity
- status (available, occupied, maintenance)
- created_at
- updated_at

**room_types**
- room_type_id (PK)
- type_name (single, double, triple)
- base_price
- amenities
- created_at

**room_amenities**
- amenity_id (PK)
- room_id (FK)
- amenity_name
- description

**room_maintenance_history**
- maintenance_id (PK)
- room_id (FK)
- maintenance_date
- description
- cost
- status

---

### Student Management Tables

**students**
- student_id (PK)
- user_id (FK)
- enrollment_number
- admission_date
- status (active, graduated, withdrawn)
- created_at

**student_profiles**
- profile_id (PK)
- student_id (FK)
- date_of_birth
- gender
- blood_group
- phone
- email
- address

**student_emergency_contacts**
- contact_id (PK)
- student_id (FK)
- contact_name
- relationship
- phone
- email

**student_documents**
- document_id (PK)
- student_id (FK)
- document_type
- file_path
- upload_date

---

### Room Allocation Tables

**room_allocations**
- allocation_id (PK)
- student_id (FK)
- room_id (FK)
- allocation_date
- release_date
- status (active, completed)
- created_at

**allocation_preferences**
- preference_id (PK)
- student_id (FK)
- room_type_preference
- floor_preference
- roommate_preference

**allocation_history**
- history_id (PK)
- student_id (FK)
- room_id (FK)
- allocation_date
- release_date

---

### Billing Tables

**fee_structures**
- structure_id (PK)
- structure_name
- academic_year
- total_fee
- created_at

**fee_components**
- component_id (PK)
- structure_id (FK)
- component_name
- amount
- description

**student_fees**
- fee_id (PK)
- student_id (FK)
- structure_id (FK)
- total_amount
- due_date
- status (pending, paid, overdue)

**invoices**
- invoice_id (PK)
- student_id (FK)
- fee_id (FK)
- invoice_date
- due_date
- amount
- status

**payments**
- payment_id (PK)
- invoice_id (FK)
- payment_date
- amount
- method (cash, card, transfer)
- transaction_id
- status

---

### Maintenance Tables

**maintenance_requests**
- request_id (PK)
- room_id (FK)
- student_id (FK)
- request_date
- description
- priority
- status (open, in_progress, completed)

**work_orders**
- order_id (PK)
- request_id (FK)
- assigned_to (FK - staff)
- start_date
- completion_date
- cost
- status

**assets**
- asset_id (PK)
- asset_name
- asset_type
- room_id (FK)
- purchase_date
- cost
- status

---

### Visitor Management Tables

**visitors**
- visitor_id (PK)
- visitor_name
- phone
- email
- id_proof_type
- id_proof_number

**visitor_passes**
- pass_id (PK)
- visitor_id (FK)
- student_id (FK)
- pass_date
- entry_time
- exit_time
- status (active, expired)

**access_logs**
- log_id (PK)
- visitor_id (FK)
- pass_id (FK)
- entry_time
- exit_time
- gate_id

**security_incidents**
- incident_id (PK)
- incident_date
- incident_type
- description
- severity
- status

---

### Attendance Tables

**attendance_records**
- record_id (PK)
- student_id (FK)
- attendance_date
- status (present, absent, leave)
- remarks

**leave_requests**
- leave_id (PK)
- student_id (FK)
- leave_type_id (FK)
- start_date
- end_date
- reason
- status (pending, approved, rejected)

**leave_types**
- type_id (PK)
- type_name
- max_days_per_year
- description

---

### Communication Tables

**announcements**
- announcement_id (PK)
- title
- content
- created_by (FK)
- created_date
- target_audience
- status

**notifications**
- notification_id (PK)
- user_id (FK)
- title
- message
- type (email, sms, push, in-app)
- sent_date
- read_date

**messages**
- message_id (PK)
- sender_id (FK)
- recipient_id (FK)
- subject
- content
- sent_date
- read_date

---

### Complaint Tables

**complaints**
- complaint_id (PK)
- student_id (FK)
- complaint_type
- description
- filed_date
- status (open, in_progress, resolved)

**complaint_resolution**
- resolution_id (PK)
- complaint_id (FK)
- resolution_date
- resolution_notes
- resolved_by (FK)

---

### Security Tables

**users**
- user_id (PK)
- username
- email
- password_hash
- role_id (FK)
- status (active, inactive)
- created_at

**roles**
- role_id (PK)
- role_name
- description

**permissions**
- permission_id (PK)
- permission_name
- description

**role_permissions**
- role_id (FK)
- permission_id (FK)

**audit_logs**
- log_id (PK)
- user_id (FK)
- action
- table_name
- record_id
- timestamp
- ip_address

---

### Reporting Tables

**reports**
- report_id (PK)
- report_name
- report_type
- created_by (FK)
- created_date
- data

**dashboard_widgets**
- widget_id (PK)
- widget_name
- widget_type
- configuration
- created_by (FK)

---

## Database Relationships

### One-to-Many
- room_types → rooms
- students → room_allocations
- rooms → room_allocations
- students → student_profiles
- students → student_documents
- students → maintenance_requests
- students → complaints
- students → attendance_records
- students → leave_requests

### Many-to-Many
- roles ↔ permissions (via role_permissions)
- students ↔ visitors (via visitor_passes)

---

## Indexing Strategy

### Primary Indexes
- All primary keys
- All foreign keys
- Frequently searched fields

### Composite Indexes
- (student_id, allocation_date)
- (room_id, status)
- (student_id, attendance_date)
- (user_id, created_date)

### Performance Indexes
- (status) on room_allocations
- (payment_status) on payments
- (complaint_status) on complaints

---

## Data Integrity

### Constraints
- Primary key constraints
- Foreign key constraints
- Unique constraints (email, username)
- Check constraints (status values)
- Not null constraints

### Triggers
- Automatic timestamp updates
- Cascade deletes
- Audit log creation
- Status validation

---

## Backup Strategy

- Daily automated backups
- Point-in-time recovery
- Multiple backup locations
- Backup testing
- Retention policy (30 days)

---

## Query Optimization

- Index usage analysis
- Query execution plans
- Slow query logging
- Connection pooling
- Query caching

---

## Database Statistics

| Metric | Count |
|--------|-------|
| **Total Tables** | 50+ |
| **Total Columns** | 300+ |
| **Primary Keys** | 50+ |
| **Foreign Keys** | 40+ |
| **Indexes** | 100+ |
| **Relationships** | 60+ |

---

**50+ tables for complete data management! 🗄️**

---
[← Previous: System Architecture](05-system-architecture.md) | [Back to Index](README.md) | [Next: API Design →](07-api-design.md)
