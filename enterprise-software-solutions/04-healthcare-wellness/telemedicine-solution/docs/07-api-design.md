# 07 - Telemedicine API Design

## Session & Media Management
- `POST /api/v1/session/init`: Generate a secure room and participant tokens.
- `GET /api/v1/session/:id/status`: Health check for active media streams.
- `POST /api/v1/session/end`: Terminate the call and trigger post-visit workflows.

## Clinical Workflow
- `POST /api/v1/consent/sign`: Record patient's legal agreement for remote care.
- `POST /api/v1/messaging/send`: Encrypted inbound message for the clinical chat.

## Remote Monitoring (RPM)
- `POST /api/v1/rpm/ingest`: Bulk upload of device/wearable data points.
- `GET /api/v1/rpm/alerts`: Fetch active clinical alerts for a patient.

## Security
- **Short-Lived Media Tokens**: Room access tokens expire 10 minutes after session end.
- **HMAC Signatures**: Required for all device-to-cloud RPM data transmissions.
- **JWE (JSON Web Encryption)**: For clinical chat payloads to ensure zero-knowledge in the database.
