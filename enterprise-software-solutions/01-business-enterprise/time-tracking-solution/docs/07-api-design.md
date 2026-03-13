# 07 - Time Tracking API Design

## Tracking Operations
- `POST /api/v1/timer/start`: Start a new active timer for a user/task.
- `POST /api/v1/timer/stop`: Capture duration and create a pending entry.
- `GET /api/v1/timer/status`: Retrieve the current user's active timer state.

## Timesheet & Approvals
- `POST /api/v1/timesheets/submit`: Group draft entries into a formal submission.
- `PATCH /api/v1/timesheets/:id/status`: Update status (Approved/Rejected).

## Rate Management
- `GET /api/v1/reports/project-margin`: Return calculated profitability based on logged hours and rates.

## Security
- **OAuth 2.0 Scopes**: `time:read`, `time:write`, `time:approve` for granular system access.
- **Idempotency**: Ensuring timer stop/start requests don't duplicate on network retry.
- **Rate Limiting**: Protecting against high-frequency pulse updates from desktop clients.

---
[← Previous: Database Design](06-database-design.md) | [Back to Index](README.md) | [Next: UI Pages →](08-ui-pages.md)
