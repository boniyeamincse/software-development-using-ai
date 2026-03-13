# 07 - Mental Health API Design

## Clinical Note Interaction
- `POST /api/v1/clinical/notes/save`: Securely submit encrypted clinical content.
- `GET /api/v1/clinical/notes/:id`: Fetch note metadata and the encrypted content blob.
- `PATCH /api/v1/clinical/notes/:id/sign`: Permanently seal a note with a digital signature.

## Crisis & Assessment
- `POST /api/v1/crisis/alert-trigger`: Immediate manual trigger for patient distress.
- `GET /api/v1/assessments/trends`: Retrieve numerical scores (e.g., PHQ-9) for progress charting.

## Telehealth & Messaging
- `POST /api/v1/telehealth/session-room`: Generate a secure, encrypted video conference token.
- `POST /api/v1/messaging/secure-send`: Transmit encrypted therapeutic homework or feedback.

## Security
- **Asymmetric Key Exchange**: Keys for decrypting notes are never transmitted in the clear; they are wrapped in the clinician's public key.
- **Field-Level Encryption**: All PII and clinical text is encrypted before hitting the database.
- **Automatic Session Timeout**: Aggressive 15-minute inactivity lock for clinical portals.

---
[← Previous: Database Design](06-database-design.md) | [Back to Index](README.md) | [Next: UI Pages →](08-ui-pages.md)
