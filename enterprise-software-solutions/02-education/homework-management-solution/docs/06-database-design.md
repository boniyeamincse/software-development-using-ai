# 06 - Homework Database Design

## Core Schema Components

### 1. Assignments
- `assignment_id`, `teacher_id`, `class_id`, `title`, `instructions`, `due_date`, `max_marks`

### 2. Submissions
- `submission_id`, `assignment_id`, `student_id`, `status` (Submitted/Pending/Late), `submitted_at`, `file_url`

### 3. Feedback & Grades
- `feedback_id`, `submission_id`, `grade`, `comments`, `voice_note_url`, `graded_at`

### 4. Resources
- `resource_id`, `assignment_id`, `type` (Link/File/Video), `url`

## Data Relationships
- **One-to-Many**: One Assignment can have many Submissions (one per student).
- **One-to-Many**: One Assignment can have multiple associated Resources.

---
[← Previous: System Architecture](05-system-architecture.md) | [Back to Index](README.md) | [Next: API Design →](07-api-design.md)
