# 07 - Customer Support API Design

## External (Channel) APIs
- `POST /api/webhooks/ingress`: Receives data from external platforms (SendGrid, WhatsApp, etc.).
- `POST /api/v1/tickets/create`: Public endpoint for web-form submissions.

## Agent Operations
- `GET /api/v1/tickets/queue`: Fetch assigned tickets with pagination and filtering.
- `POST /api/v1/tickets/:id/reply`: Add a response and update ticket status.
- `PATCH /api/v1/tickets/:id/assign`: Transfer ticket to another agent or group.

## Help Center
- `GET /api/v1/kb/search`: Search knowledge base articles.
- `GET /api/v1/kb/categories`: Fetch article groupings.

## Security
- **OAuth 2.0**: For agent authentication.
- **API Scopes**: `tickets.read`, `tickets.admin`, `settings.write`.

---
[← Previous: Database Design](06-database-design.md) | [Back to Index](README.md) | [Next: UI Pages →](08-ui-pages.md)
