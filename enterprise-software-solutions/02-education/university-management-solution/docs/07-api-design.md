# 07 - University API Design

## Registrar Endpoints
- `GET /api/registrar/degree-audit/:student_id`: Calculate remaining credits for graduation.
- `PATCH /api/registrar/enroll`: Atomic transaction for course selection.

## Research & Faculty
- `POST /api/research/publish`: Upload metadata for new research paper.
- `GET /api/faculty/workload/:faculty_id`: Aggregate teaching vs research hours.

## Financial aid
- `GET /api/finaid/eligibility/:student_id`: Boolean check for specific scholarship criteria.

## Integration Protocols
- **SAML 2.0 / SSO**: Central authentication for all campus services.
- **LTI (Learning Tools Interoperability)**: Standard for hooking in external lab simulators or e-books.

---
[← Previous: Database Design](06-database-design.md) | [Back to Index](README.md) | [Next: UI Pages →](08-ui-pages.md)
