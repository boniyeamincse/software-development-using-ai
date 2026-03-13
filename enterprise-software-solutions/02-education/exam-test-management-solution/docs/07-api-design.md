# 07 - Exam API Design

## Assessment Lifecycle
- `POST /api/assess/init`: Perform system checks and start the exam timer.
- `POST /api/assess/sync`: Bulk-save answers during the exam (incremental sync).
- `POST /api/assess/finalize`: Final submission with integrity hash.

## Proctoring Telemetry
- `POST /api/proctor/vibe-check`: Send hardware status (Camera/Mic).
- `POST /api/proctor/incident`: Flag a specific student for manual review.

## Management Endpoints
- `GET /api/coe/stats/:exam_id`: Real-time view of student submission status.
- `PUT /api/evaluation/submit-grade`: For manual evaluators to post scores.

---
[← Previous: Database Design](06-database-design.md) | [Back to Index](README.md) | [Next: UI Pages →](08-ui-pages.md)
