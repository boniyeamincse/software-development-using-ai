# 07 - Patient Feedback API Design

## Survey Interaction
- `POST /api/v1/surveys/submit`: Inbound endpoint for patient feedback payloads.
- `GET /api/v1/surveys/render/:id`: Fetch specific survey structure and logic for the frontend.
- `POST /api/v1/contact/opt-out`: Patient-driven suppression for future survey requests.

## Management & Analytics
- `GET /api/v1/scores/facility`: Fetch real-time NPS/CSAT for a whole facility.
- `GET /api/v1/theme-trends`: Retrieve the top 5 emerging feedback keywords.
- `PATCH /api/v1/cases/:id/resolve`: Submit a resolution for a negative patient complaint.

## Data Ingestion
- `POST /api/v1/ehr-trigger`: Inbound webhook from hospital EHR systems to initiate a survey.

## Security
- **Anonymity Tokens**: Unique, short-lived tokens for survey links that do not expose the patient's ID in the URL.
- **Strict Data Siloing**: Clinical management staff CANNOT view the `patient_identity` field if the survey was marked "Anonymous."
- **WAF Protection**: Shielding the survey submission endpoint from bot-driven "Review Bombing."

---
[← Previous: Database Design](06-database-design.md) | [Back to Index](README.md) | [Next: UI Pages →](08-ui-pages.md)
