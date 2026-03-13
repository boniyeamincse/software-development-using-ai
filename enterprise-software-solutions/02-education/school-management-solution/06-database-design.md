# 06 - Database Design

## Core Entities

### 1. Users
- `id`, `email`, `password_hash`, `role_id`, `status`

### 2. Students
- `id`, `user_id`, `admission_no`, `first_name`, `last_name`, `date_of_birth`, `class_id`, `parent_id`

### 3. Classes
- `id`, `name`, `section`, `room_number`, `teacher_id`

### 4. Attendance
- `id`, `student_id`, `date`, `status` (Present/Absent/Late), `remarks`

### 5. Fees
- `id`, `student_id`, `amount`, `due_date`, `payment_status`

## Key Relationships
- **One-to-Many**: One Class has many Students.
- **One-to-Many**: One Parent can have multiple Students (wards).
- **Many-to-Many**: Students and Courses (via Enrollment table).
