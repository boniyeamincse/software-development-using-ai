# 07 - Pharmacy API Design

## Prescription & Clinical
- `POST /api/v1/prescriptions/ingest`: Receive a new e-prescription from external hospital systems.
- `GET /api/v1/clinical/interactions`: Check a prospective dispense against the patient's history.
- `POST /api/v1/dispense/verify`: Trigger the triple-barcode check and clinical finalization.

## Inventory & Supply Chain
- `GET /api/v1/inventory/stock-status`: Fetch live stock levels for a specific branch.
- `POST /api/v1/inventory/transfer`: Initiate an internal stock move between branches.
- `PATCH /api/v1/batch/waste`: Mark specific stock as expired or damaged with reason codes.

## Financial
- `POST /api/v1/insurance/adjudicate`: Real-time submission of a claim to the payer.

## Security
- **Biometric WebAuthn**: Required for all narcotics-related API calls.
- **Field-Level Encryption**: Encrypting `patient_pill_usage` and `narcotic_history` in the database.
- **Strict IP Whitelisting**: Restricting dispensing APIs to authorized pharmacy terminals only.
