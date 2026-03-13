# 11 - Time Tracking Security & Data Privacy

## Data Integrity
- **Locking Logic**: Once a timesheet is approved or billing is generated, the system creates a "Hard Lock," preventing any downstream modification of the original hours.
- **Immutable Audit Trail**: Every change to a time log (e.g., editing duration) is recorded with "Before/After" snapshots and user attribution.

## Privacy
- **Selective Data Masking**: External clients can see billable totals but not the granular employee-level cost rates.
- **Location Privacy**: GPS tracking for mobile is only active during the explicit "Timer Running" state.

## Compliance
- **SOC 2 Type II**: Adhering to strict data protection and availability protocols.
- **Labor Law Automation**: Pre-built logic modules that enforce local overtime and break regulations automatically.

---
[← Previous: Technology Stack](10-tech-stack.md) | [Back to Index](README.md) | [Next: Deployment Strategy →](12-deployment.md)
