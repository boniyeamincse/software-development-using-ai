# 07 - Clinic API Design

## Scheduling & Front-Desk
- `GET /api/v1/availability`: Fetch open slots based on provider and specialty.
- `POST /api/v1/booking/confirm`: Book a patient slot and trigger notification.
- `PATCH /api/v1/check-in/:id`: Mark patient as "Waiting" and notify medical assistant.

## Clinical & Charting
- `POST /api/v1/encounters/save-draft`: Periodically save SOAP note progress.
- `GET /api/v1/patients/:id/summary`: Retrieve a "One-Page" clinical history.

## Billing
- `POST /api/v1/bills/generate`: Create an invoice based on recorded CPT codes.
- `GET /api/v1/insurance/verify`: Real-time eligibility check for the patient's card.

## Security
- **Scoped API Tokens**: Third-party lab integrations use tokens restricted to their `lab_id`.
- **MFA Enforcement**: Mandatory for all clinical accounts.
- **HIPAA Activity Log**: All clinical data access is logged to an immutable cloud stream.
