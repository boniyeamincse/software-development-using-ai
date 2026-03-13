# 06 - University Database Design

## Specialty Schema Components

### 1. Research Grants
- `grant_id`, `pi_id` (Principal Investigator), `amount`, `funder`, `start_date`, `end_date`

### 2. Credit Logs
- `log_id`, `student_id`, `course_id`, `credits_earned`, `semester_index`

### 3. Faculty Portfolios
- `faculty_id`, `publication_links`, `tenure_status`, `department_head_flag`

### 4. Course Catalog
- `course_code`, `title`, `credits`, `prerequisite_code`, `faculty_id`

## Complex Relationships
- **Self-Referencing**: Course table links to itself for prerequisite chains.
- **Many-to-Many**: Faculty to Research Projects (Collaborative researchers).
- **Polymorphic**: Financial transactions that can be "Tuition," "Grant Refund," or "Fines."

---
[← Previous: System Architecture](05-system-architecture.md) | [Back to Index](README.md) | [Next: API Design →](07-api-design.md)
