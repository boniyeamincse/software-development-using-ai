# 06 - Project Database Design

## Core Schema Components

### 1. Projects & Portfolios
- `project_id`, `name`, `status` (Planning/Active/Completed), `start_date`, `end_date`, `budget`
- `portfolio_id`, `owner_id`, `strategic_alignment`

### 2. Tasks & Dependencies
- `task_id`, `project_id`, `parent_task_id`, `title`, `assignee_id`, `status`
- `dependency_id`, `task_id`, `depends_on_task_id`, `dependency_type` (e.g., FS)

### 3. Resources & Capacity
- `user_profile_id`, `department_id`, `base_capacity_hours`, `skills_json`
- `allocation_id`, `task_id`, `user_id`, `hours_planned`, `hours_actual`

### 4. Collaboration
- `comment_id`, `task_id`, `user_id`, `content_md`, `created_at`
- `attachment_id`, `task_id`, `s3_url`, `version_no`

## Key Relationships
- **One-to-Many**: One Project contains many Tasks.
- **Self-Referential**: Tasks can be parents of other Tasks (Sub-tasks).
- **Many-to-Many**: Users can be assigned to multiple Tasks; Tasks can have multiple Users.
