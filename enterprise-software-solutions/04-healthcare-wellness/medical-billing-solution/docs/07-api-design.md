# 07 - Medical Billing API Design

## Claim Ingestion & Submission
- `POST /api/v1/claims/import`: Ingest clinical encounter data from an EHR system.
- `POST /api/v1/claims/scrub`: Manually trigger the validation engine for a batch.
- `GET /api/v1/claims/:id/status`: Real-time tracking of the claim in the clearinghouse.

## Financial & Reconciliation
- `POST /api/v1/remittance/post-era`: Process an inbound 835 file and update ledgers.
- `POST /api/v1/payments/patient-collect`: Process a credit card payment via integrated gateway.

## Eligibility & Verification
- `GET /api/v1/eligibility/check`: Real-time 270/271 request for the patient's insurance card.

## Security
- **Strict PII Scoping**: Billing APIs only expose financial-relevant data; sensitive clinical SOAP notes are not transmitted.
- **HMAC + JWE**: For all EDI payloads to ensure integrity and privacy during transmission.
- **IP Whitelisting**: Restricting API access to authorized EHR and Clearinghouse endpoints.
