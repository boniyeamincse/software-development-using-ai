# 07 - Project API Design

## Task & Workflow
- `POST /api/v1/tasks`: Create a new task within a project.
- `PATCH /api/v1/tasks/:id/move`: Update task status or move to a different sprint/stage.
- `GET /api/v1/projects/:id/critical-path`: Calculate and return the project's longest logical path.

## Collaboration & Content
- `POST /api/v1/tasks/:id/comments`: Add a comment with @mention logic.
- `GET /api/v1/activities/feed`: Fetch real-time updates for a specific project.

## Resource Analytics
- `GET /api/v1/team/workload`: Retrieve capacity data for resource balancing.

## Security
- **Websocket Authentication**: Signed tokens for secure real-time connections.
- **Scoped API Keys**: For integrating with CI/CD or other external automation tools.

---
[← Previous: Database Design](06-database-design.md) | [Back to Index](README.md) | [Next: UI Pages →](08-ui-pages.md)
