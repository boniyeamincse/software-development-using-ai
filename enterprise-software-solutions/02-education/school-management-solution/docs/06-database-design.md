# School Management System - Database Design

## 1. Database Overview

The School Management System uses a **relational database** (MySQL 8.0+ or PostgreSQL 12+) with normalized schema following **3NF (Third Normal Form)** principles.

### Database Connection Details:
- **Engine**: MySQL or PostgreSQL
- **Character Set**: UTF-8 (UTF-8MB4 for MySQL)
- **Collation**: utf8mb4_unicode_ci (or equivalent)
- **Connection Pool**: 20-50 connections
- **Backup**: Daily automated backups

---

## 2. Entity-Relationship Diagram (ERD)

```
┌────────────────┐
│     users      │
├────────────────┤
│ id (PK)        │
│ username       │
│ email (UQ)     │
│ password_hash  │
│ first_name     │
│ last_name      │
│ is_active      │
│ created_at     │
│ updated_at     │
└────────────────┘
       │
       ├─────────────────────────┬──────────────────────┐
       │                         │                      │
   1:M │                         │                      │
       ↓                         ↓                      ↓
┌────────────────┐      ┌────────────────┐    ┌─────────────────┐
│   students     │      │    teachers    │    │   accountants   │
├────────────────┤      ├────────────────┤    ├─────────────────┤
│ id (PK)        │      │ id (PK)        │    │ id (PK)         │
│ user_id (FK)   │      │ user_id (FK)   │    │ user_id (FK)    │
│ roll_number    │      │ employee_id    │    │ department      │
│ dob            │      │ qualification  │    │ hire_date       │
│ address        │      │ hire_date      │    │ status          │
│ class_id (FK)  │      │ status         │    │ created_at      │
│ created_at     │      │ created_at     │    │ updated_at      │
│ updated_at     │      │ updated_at     │    └─────────────────┘
└────────────────┘      └────────────────┘
       │                       │
       │ 1:M                   │ 1:M
       ↓                       ↓
    ┌──────────────────────┐   ┌──────────────────────┐
    │    attendance        │   │  teacher_assignments │
    ├──────────────────────┤   ├──────────────────────┤
    │ id (PK)              │   │ id (PK)              │
    │ student_id (FK)      │   │ teacher_id (FK)      │
    │ class_id (FK)        │   │ class_id (FK)        │
    │ date                 │   │ subject_id (FK)      │
    │ is_present           │   │ academic_year        │
    │ marked_by (FK)       │   │ created_at           │
    │ marked_at            │   └──────────────────────┘
    │ created_at           │
    │ updated_at           │
    └──────────────────────┘

┌────────────────┐         ┌─────────────────┐
│    classes     │         │    subjects     │
├────────────────┤         ├─────────────────┤
│ id (PK)        │1       M│ id (PK)         │
│ name           │─────────│ name            │
│ section        │         │ code            │
│ academic_year  │         │ description     │
│ capacity       │         │ created_at      │
│ class_teacher  │         │ updated_at      │
│ created_at     │         └─────────────────┘
│ updated_at     │
└────────────────┘
       │
       │ 1:M
       ↓
┌──────────────────────┐
│ class_subjects       │
├──────────────────────┤
│ id (PK)              │
│ class_id (FK)        │
│ subject_id (FK)      │
│ created_at           │
└──────────────────────┘

┌──────────────────┐
│     exams        │
├──────────────────┤
│ id (PK)          │
│ name             │
│ class_id (FK)    │
│ subject_id (FK)  │
│ exam_date        │
│ start_time       │
│ end_time         │
│ total_marks      │
│ passing_marks    │
│ created_at       │
└──────────────────┘
       │
       │ 1:M
       ↓
┌─────────────────────┐
│     results         │
├─────────────────────┤
│ id (PK)             │
│ student_id (FK)     │
│ exam_id (FK)        │
│ marks_obtained      │
│ percentage          │
│ grade               │
│ status              │
│ entered_by (FK)     │
│ entered_at          │
│ published_at        │
│ created_at          │
│ updated_at          │
└─────────────────────┘

┌─────────────────────┐
│ fee_structures      │
├─────────────────────┤
│ id (PK)             │
│ name                │
│ class_id (FK)       │
│ academic_year       │
│ total_amount        │
│ created_at          │
│ updated_at          │
└─────────────────────┘
       │
       │ 1:M
       ↓
┌──────────────────────┐
│ fee_components       │
├──────────────────────┤
│ id (PK)              │
│ fee_structure_id(FK) │
│ component_name       │
│ amount               │
│ created_at           │
└──────────────────────┘

┌──────────────────────┐
│ student_fees         │
├──────────────────────┤
│ id (PK)              │
│ student_id (FK)      │
│ fee_structure_id(FK) │
│ total_amount         │
│ amount_paid          │
│ due_date             │
│ status               │
│ created_at           │
│ updated_at           │
└──────────────────────┘
       │
       │ 1:M
       ↓
┌──────────────────────┐
│ fee_payments         │
├──────────────────────┤
│ id (PK)              │
│ student_fee_id (FK)  │
│ amount               │
│ payment_method       │
│ transaction_id       │
│ paid_date            │
│ recorded_by (FK)     │
│ created_at           │
└──────────────────────┘
```

---

## 3. Table Schemas

### 3.1 Core User Management Tables

#### users
```sql
CREATE TABLE users (
  id BIGINT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
  username VARCHAR(100) UNIQUE NOT NULL,
  email VARCHAR(100) UNIQUE NOT NULL,
  password_hash VARCHAR(255) NOT NULL,
  first_name VARCHAR(100) NOT NULL,
  last_name VARCHAR(100) NOT NULL,
  phone VARCHAR(20),
  profile_photo_url VARCHAR(255),
  is_active BOOLEAN DEFAULT TRUE,
  last_login_at TIMESTAMP NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  
  KEY idx_email (email),
  KEY idx_username (username),
  KEY idx_is_active (is_active)
) CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

#### roles
```sql
CREATE TABLE roles (
  id BIGINT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
  name VARCHAR(100) UNIQUE NOT NULL,
  description TEXT,
  is_active BOOLEAN DEFAULT TRUE,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
) CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

#### user_roles
```sql
CREATE TABLE user_roles (
  id BIGINT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
  user_id BIGINT UNSIGNED NOT NULL,
  role_id BIGINT UNSIGNED NOT NULL,
  assigned_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  
  FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE,
  FOREIGN KEY (role_id) REFERENCES roles(id) ON DELETE CASCADE,
  UNIQUE KEY unique_user_role (user_id, role_id),
  KEY idx_user_id (user_id),
  KEY idx_role_id (role_id)
) CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

#### permissions
```sql
CREATE TABLE permissions (
  id BIGINT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
  name VARCHAR(100) UNIQUE NOT NULL,
  description TEXT,
  module VARCHAR(100),
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
) CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

#### role_permissions
```sql
CREATE TABLE role_permissions (
  id BIGINT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
  role_id BIGINT UNSIGNED NOT NULL,
  permission_id BIGINT UNSIGNED NOT NULL,
  granted_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  
  FOREIGN KEY (role_id) REFERENCES roles(id) ON DELETE CASCADE,
  FOREIGN KEY (permission_id) REFERENCES permissions(id) ON DELETE CASCADE,
  UNIQUE KEY unique_role_permission (role_id, permission_id)
) CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

---

### 3.2 Academic Management Tables

#### classes
```sql
CREATE TABLE classes (
  id BIGINT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
  name VARCHAR(50) NOT NULL,
  section VARCHAR(10),
  academic_year VARCHAR(9) NOT NULL,
  capacity INT UNSIGNED,
  class_teacher_id BIGINT UNSIGNED,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  
  FOREIGN KEY (class_teacher_id) REFERENCES teachers(id) ON DELETE SET NULL,
  UNIQUE KEY unique_class_section_year (name, section, academic_year),
  KEY idx_academic_year (academic_year)
) CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

#### students
```sql
CREATE TABLE students (
  id BIGINT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
  user_id BIGINT UNSIGNED NOT NULL,
  roll_number VARCHAR(50) UNIQUE NOT NULL,
  class_id BIGINT UNSIGNED NOT NULL,
  date_of_birth DATE NOT NULL,
  gender ENUM('M', 'F', 'Other'),
  address TEXT,
  city VARCHAR(100),
  state VARCHAR(100),
  postal_code VARCHAR(20),
  emergency_contact_name VARCHAR(100),
  emergency_contact_phone VARCHAR(20),
  status ENUM('Active', 'Inactive', 'Withdrawn', 'Transferred') DEFAULT 'Active',
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  
  FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE,
  FOREIGN KEY (class_id) REFERENCES classes(id),
  UNIQUE KEY unique_roll_number (roll_number),
  KEY idx_class_id (class_id),
  KEY idx_status (status)
) CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

#### teachers
```sql
CREATE TABLE teachers (
  id BIGINT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
  user_id BIGINT UNSIGNED NOT NULL,
  employee_id VARCHAR(50) UNIQUE NOT NULL,
  qualification VARCHAR(255),
  specialization VARCHAR(100),
  hire_date DATE NOT NULL,
  status ENUM('Active', 'Inactive', 'On Leave', 'Retired') DEFAULT 'Active',
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  
  FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE,
  KEY idx_status (status)
) CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

#### subjects
```sql
CREATE TABLE subjects (
  id BIGINT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
  name VARCHAR(100) NOT NULL,
  code VARCHAR(20) UNIQUE NOT NULL,
  description TEXT,
  credit_hours INT UNSIGNED,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
) CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

#### class_subjects
```sql
CREATE TABLE class_subjects (
  id BIGINT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
  class_id BIGINT UNSIGNED NOT NULL,
  subject_id BIGINT UNSIGNED NOT NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  
  FOREIGN KEY (class_id) REFERENCES classes(id) ON DELETE CASCADE,
  FOREIGN KEY (subject_id) REFERENCES subjects(id) ON DELETE CASCADE,
  UNIQUE KEY unique_class_subject (class_id, subject_id)
) CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

#### teacher_assignments
```sql
CREATE TABLE teacher_assignments (
  id BIGINT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
  teacher_id BIGINT UNSIGNED NOT NULL,
  class_id BIGINT UNSIGNED NOT NULL,
  subject_id BIGINT UNSIGNED NOT NULL,
  academic_year VARCHAR(9) NOT NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  
  FOREIGN KEY (teacher_id) REFERENCES teachers(id) ON DELETE CASCADE,
  FOREIGN KEY (class_id) REFERENCES classes(id) ON DELETE CASCADE,
  FOREIGN KEY (subject_id) REFERENCES subjects(id) ON DELETE CASCADE,
  KEY idx_teacher_id (teacher_id),
  KEY idx_class_id (class_id),
  KEY idx_academic_year (academic_year)
) CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

---

### 3.3 Attendance Tables

#### attendance_records
```sql
CREATE TABLE attendance_records (
  id BIGINT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
  student_id BIGINT UNSIGNED NOT NULL,
  class_id BIGINT UNSIGNED NOT NULL,
  attendance_date DATE NOT NULL,
  status ENUM('Present', 'Absent', 'Late', 'Leave') NOT NULL,
  marked_by BIGINT UNSIGNED NOT NULL,
  remarks TEXT,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  
  FOREIGN KEY (student_id) REFERENCES students(id) ON DELETE CASCADE,
  FOREIGN KEY (class_id) REFERENCES classes(id),
  FOREIGN KEY (marked_by) REFERENCES users(id),
  UNIQUE KEY unique_attendance (student_id, class_id, attendance_date),
  KEY idx_student_id (student_id),
  KEY idx_date (attendance_date),
  KEY idx_status (status)
) CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

#### leave_types
```sql
CREATE TABLE leave_types (
  id BIGINT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
  name VARCHAR(100) NOT NULL,
  code VARCHAR(20) UNIQUE,
  description TEXT,
  requires_approval BOOLEAN DEFAULT FALSE,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
) CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

#### attendance_leaves
```sql
CREATE TABLE attendance_leaves (
  id BIGINT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
  student_id BIGINT UNSIGNED NOT NULL,
  leave_type_id BIGINT UNSIGNED NOT NULL,
  start_date DATE NOT NULL,
  end_date DATE NOT NULL,
  reason TEXT,
  status ENUM('Pending', 'Approved', 'Rejected') DEFAULT 'Pending',
  approved_by BIGINT UNSIGNED,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  
  FOREIGN KEY (student_id) REFERENCES students(id) ON DELETE CASCADE,
  FOREIGN KEY (leave_type_id) REFERENCES leave_types(id),
  FOREIGN KEY (approved_by) REFERENCES users(id),
  KEY idx_student_id (student_id),
  KEY idx_status (status)
) CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

---

### 3.4 Examination & Results Tables

#### exams
```sql
CREATE TABLE exams (
  id BIGINT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
  name VARCHAR(100) NOT NULL,
  class_id BIGINT UNSIGNED NOT NULL,
  subject_id BIGINT UNSIGNED,
  exam_date DATE NOT NULL,
  start_time TIME NOT NULL,
  end_time TIME NOT NULL,
  total_marks INT UNSIGNED NOT NULL,
  passing_marks INT UNSIGNED NOT NULL,
  exam_type ENUM('Unit Test', 'Mid Term', 'Final', 'Practical') NOT NULL,
  academic_year VARCHAR(9) NOT NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  
  FOREIGN KEY (class_id) REFERENCES classes(id),
  FOREIGN KEY (subject_id) REFERENCES subjects(id),
  KEY idx_exam_date (exam_date),
  KEY idx_academic_year (academic_year),
  KEY idx_class_id (class_id)
) CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

#### results
```sql
CREATE TABLE results (
  id BIGINT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
  student_id BIGINT UNSIGNED NOT NULL,
  exam_id BIGINT UNSIGNED NOT NULL,
  marks_obtained DECIMAL(6, 2),
  percentage DECIMAL(5, 2),
  grade VARCHAR(2),
  status ENUM('Pass', 'Fail', 'Incomplete') NOT NULL,
  entered_by BIGINT UNSIGNED NOT NULL,
  entered_at TIMESTAMP,
  published_at TIMESTAMP NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  
  FOREIGN KEY (student_id) REFERENCES students(id) ON DELETE CASCADE,
  FOREIGN KEY (exam_id) REFERENCES exams(id) ON DELETE CASCADE,
  FOREIGN KEY (entered_by) REFERENCES users(id),
  UNIQUE KEY unique_result (student_id, exam_id),
  KEY idx_student_id (student_id),
  KEY idx_status (status),
  KEY idx_published_at (published_at)
) CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

#### grades
```sql
CREATE TABLE grades (
  id BIGINT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
  name VARCHAR(2) UNIQUE NOT NULL,
  min_percentage DECIMAL(5, 2),
  max_percentage DECIMAL(5, 2),
  description VARCHAR(100),
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
) CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

---

### 3.5 Fee Management Tables

#### fee_structures
```sql
CREATE TABLE fee_structures (
  id BIGINT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
  name VARCHAR(100) NOT NULL,
  class_id BIGINT UNSIGNED,
  academic_year VARCHAR(9) NOT NULL,
  total_amount DECIMAL(10, 2) NOT NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  
  FOREIGN KEY (class_id) REFERENCES classes(id),
  UNIQUE KEY unique_fee_structure (class_id, academic_year)
) CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

#### fee_components
```sql
CREATE TABLE fee_components (
  id BIGINT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
  fee_structure_id BIGINT UNSIGNED NOT NULL,
  component_name VARCHAR(100) NOT NULL,
  amount DECIMAL(10, 2) NOT NULL,
  description TEXT,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  
  FOREIGN KEY (fee_structure_id) REFERENCES fee_structures(id) ON DELETE CASCADE,
  KEY idx_fee_structure_id (fee_structure_id)
) CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

#### student_fees
```sql
CREATE TABLE student_fees (
  id BIGINT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
  student_id BIGINT UNSIGNED NOT NULL,
  fee_structure_id BIGINT UNSIGNED NOT NULL,
  total_amount DECIMAL(10, 2) NOT NULL,
  amount_paid DECIMAL(10, 2) DEFAULT 0,
  discount_amount DECIMAL(10, 2) DEFAULT 0,
  due_date DATE NOT NULL,
  status ENUM('Pending', 'Partial', 'Paid', 'Overdue') DEFAULT 'Pending',
  academic_year VARCHAR(9) NOT NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  
  FOREIGN KEY (student_id) REFERENCES students(id) ON DELETE CASCADE,
  FOREIGN KEY (fee_structure_id) REFERENCES fee_structures(id),
  KEY idx_student_id (student_id),
  KEY idx_status (status),
  KEY idx_due_date (due_date),
  KEY idx_academic_year (academic_year)
) CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

#### fee_payments
```sql
CREATE TABLE fee_payments (
  id BIGINT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
  student_fee_id BIGINT UNSIGNED NOT NULL,
  amount DECIMAL(10, 2) NOT NULL,
  payment_method ENUM('Cash', 'Check', 'Credit Card', 'Bank Transfer') NOT NULL,
  transaction_id VARCHAR(100),
  paid_date DATE NOT NULL,
  recorded_by BIGINT UNSIGNED NOT NULL,
  notes TEXT,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  
  FOREIGN KEY (student_fee_id) REFERENCES student_fees(id) ON DELETE CASCADE,
  FOREIGN KEY (recorded_by) REFERENCES users(id),
  KEY idx_student_fee_id (student_fee_id),
  KEY idx_paid_date (paid_date)
) CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

---

### 3.6 Notification & Communication Tables

#### notifications
```sql
CREATE TABLE notifications (
  id BIGINT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
  user_id BIGINT UNSIGNED NOT NULL,
  subject VARCHAR(255) NOT NULL,
  message TEXT NOT NULL,
  type ENUM('Info', 'Warning', 'Alert', 'Success') DEFAULT 'Info',
  is_read BOOLEAN DEFAULT FALSE,
  read_at TIMESTAMP NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  
  FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE,
  KEY idx_user_id (user_id),
  KEY idx_is_read (is_read)
) CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

#### notification_templates
```sql
CREATE TABLE notification_templates (
  id BIGINT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
  name VARCHAR(100) UNIQUE NOT NULL,
  subject VARCHAR(255) NOT NULL,
  body TEXT NOT NULL,
  variables JSON,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
) CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

---

### 3.7 Holiday & Calendar Tables

#### academic_calendars
```sql
CREATE TABLE academic_calendars (
  id BIGINT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
  academic_year VARCHAR(9) UNIQUE NOT NULL,
  start_date DATE NOT NULL,
  end_date DATE NOT NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
) CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

#### holidays
```sql
CREATE TABLE holidays (
  id BIGINT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
  name VARCHAR(100) NOT NULL,
  holiday_date DATE NOT NULL,
  holiday_type ENUM('Public Holiday', 'School Holiday', 'Vacation') NOT NULL,
  description TEXT,
  academic_year VARCHAR(9),
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  
  FOREIGN KEY (academic_year) REFERENCES academic_calendars(academic_year),
  KEY idx_holiday_date (holiday_date)
) CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

---

## 4. Indexing Strategy

### High-Priority Indexes
```sql
-- User authentication
CREATE INDEX idx_users_email ON users(email);
CREATE INDEX idx_users_username ON users(username);

-- Student queries
CREATE INDEX idx_students_class_id ON students(class_id);
CREATE INDEX idx_students_status ON students(status);

-- Attendance queries
CREATE INDEX idx_attendance_student ON attendance_records(student_id);
CREATE INDEX idx_attendance_date ON attendance_records(attendance_date);
CREATE INDEX idx_attendance_class ON attendance_records(class_id);

-- Result queries
CREATE INDEX idx_results_student ON results(student_id);
CREATE INDEX idx_results_exam ON results(exam_id);
CREATE INDEX idx_results_status ON results(status);

-- Fee queries
CREATE INDEX idx_student_fees_student ON student_fees(student_id);
CREATE INDEX idx_student_fees_status ON student_fees(status);
```

---

## 5. Data Integrity Constraints

### Foreign Key Constraints
- All user type tables (students, teachers) reference users table
- All transaction tables reference user table for audit trail
- Cascading deletes for related records
- Set NULL for optional references

### Unique Constraints
- Email addresses (unique across users)
- Student roll numbers
- Teacher employee IDs
- Username uniqueness

---

## 6. Summary

The database design follows relational database best practices with:
- Proper normalization (3NF)
- Comprehensive indexing for query performance
- Referential integrity through foreign keys
- Audit trail through timestamps and user references
- ENUM types for status fields
- Proper data types for financial and date information

