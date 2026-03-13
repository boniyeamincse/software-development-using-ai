# 07 - HRMS API Design

## Personnel & Org
- `POST /api/v1/employees/onboard`: Trigger the onboarding workflow for a new hire.
- `GET /api/v1/org/hierarchy`: Retrieve the full reporting structure for visualization.

## Time & Leave
- `POST /api/v1/leave/request`: Submit a new leave application.
- `PATCH /api/v1/leave/approve/:id`: Manager action to approve/reject leave.

## Payroll Access
- `GET /api/v1/payroll/payslips`: Retrieve historical payslips (ESS context).
- `POST /api/v1/payroll/generate`: HR-only trigger to calculate current period wages.

## Security
- **JWT (JSON Web Tokens)**: For stateless authentication of frontend users.
- **MFA (Multi-Factor Authentication)**: Required for all HR-level and Financial-level API operations.
- **CORS Policies**: Restricted to company-approved domains to prevent external scripts from accessing personnel data.

---
[← Previous: Database Design](06-database-design.md) | [Back to Index](README.md) | [Next: UI Pages →](08-ui-pages.md)
