# 07 - Homework API Design

## Submission Flow
- `GET /api/homework/student/:student_id`: Fetch all active and overdue assignments.
- `POST /api/homework/submit`: Upload homework file and metadata.
- `GET /api/homework/resource/:id`: Generate presigned URL for secure resource download.

## Grading Lifecycle
- `GET /api/teacher/pending-grading`: List all ungraded submissions for a class.
- `POST /api/teacher/grade`: Submit score and structured feedback.

## Notifications
- `POST /api/notify/reminder`: Trigger manual or automated nudge to students.

## Security
- **JWT Auth**: Mandatory for all endpoints.
- **Scoped access**: Students cannot view other students' submissions or teacher feedback until released.
