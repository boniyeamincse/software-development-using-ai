# 06 - Exam Database Design

## Core Schema Components

### 1. Question Bank
- `q_id`, `subject_id`, `type` (MCQ/Desc), `content` (HTML/LaTeX), `answer_key`, `difficulty`

### 2. Exam Schedules
- `exam_id`, `title`, `start_time`, `duration`, `marks_weightage`, `proctoring_enabled`

### 3. Student Responses
- `response_id`, `student_id`, `exam_id`, `q_id`, `selected_option`, `descriptive_answer`, `snapshot_url` (proctoring evidence)

### 4. Grading Rubrics
- `rubric_id`, `q_id`, `criteria`, `max_marks`

## Data Relationships
- **Composite Pattern**: For complex questions with sub-parts.
- **Audit Table**: Tracking every keystroke and system action during the exam window.

---
[← Previous: System Architecture](05-system-architecture.md) | [Back to Index](README.md) | [Next: API Design →](07-api-design.md)
