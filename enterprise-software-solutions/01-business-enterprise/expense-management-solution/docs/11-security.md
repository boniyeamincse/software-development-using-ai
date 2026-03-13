# 11 - Expense Security & Fraud Prevention

## Data Integrity & Safety
- **Encrypted Storage**: Every receipt image is encrypted at rest using AES-256.
- **Immutable Entry Logs**: Once an expense item is "Approved," it cannot be modified; only "Adjustment Entries" can be created by Finance.

## Fraud Prevention
- **Duplicate Detection AI**: Hashing receipt images and comparing metadata to identify double-submissions across the entire company.
- **Anomaly Detection**: Flagging "After-Hours Spending" or "Sequential Receipt Nos" from the same vendor.

## Access Control
- **RBAC**: Ensuring managers can only see their direct reports' expenses.
- **Signed URLs**: Receipt access links are short-lived and tied to specific user sessions.
- **Audit Logging**: Tracking every instance of a receipt being viewed, downloaded, or modified.

---
[← Previous: Technology Stack](10-tech-stack.md) | [Back to Index](README.md) | [Next: Deployment Strategy →](12-deployment.md)
