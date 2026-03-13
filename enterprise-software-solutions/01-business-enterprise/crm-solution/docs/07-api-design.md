# 07 - CRM API Design

## Lead & Opportunity
- `POST /api/v1/leads/ingest`: Endpoint for web-to-lead forms.
- `PATCH /api/v1/opportunities/:id/stage`: Update deal progress.
- `GET /api/v1/forecast/weighted`: Calculate revenue based on probability.

## Communication
- `POST /api/v1/activities/call/log`: Register a completed VoIP call.
- `GET /api/v1/contacts/:id/timeline`: Fetch unified interaction history.

## Automation & Events
- `POST /api/v1/automation/trigger`: Manually trigger a specific sales cadence.

## Security
- **OAuth 2.0**: For authorizing 3rd-party integrations (e.g., Gmail/Outlook).
- **Scope-Based Access**: Ensuring API keys only have access to relevant modules (e.g., Marketing-only).
