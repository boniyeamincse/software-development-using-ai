# 07 - Hospital API Design

## Clinical Encounters
- `POST /api/v1/encounters/admit`: Initiate a new patient care session (Inpatient/Outpatient).
- `GET /api/v1/patients/:mrn/chart`: Retrieve a FHIR-compliant summary of the patient record.
- `POST /api/v1/clinical/vitals`: Batch ingestion of bedside monitor data.

## Orders & Diagnostics
- `POST /api/v1/orders/new`: Submit a new physician order (Stat/Stat-stat).
- `GET /api/v1/lab/results/:id`: Retrieve finalized lab reports and reference ranges.

## Facility Management
- `GET /api/v1/facility/bed-status`: Live inventory of available treatment spots.

## Health Interoperability (Compliance)
- **HL7 v2 / FHIR R4**: Standardized endpoints for sharing data with external providers.
- **DICOM Web**: Secure API for retrieving and viewing medical imaging.
- **HIPAA Audit Log**: Every GET request on patient data is logged with `user_id` and `purpose_code`.

---
[← Previous: Database Design](06-database-design.md) | [Back to Index](README.md) | [Next: UI Pages →](08-ui-pages.md)
