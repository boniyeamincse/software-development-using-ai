# 11 - Accounting Security & Internal Controls

## Data Integrity
- **Double-Entry Enforcement**: The system logic physically prevents saving any transaction where Sum(Debit) != Sum(Credit).
- **Immutable Ledger**: Once a financial period is closed, records cannot be edited—only adjusting entries can be made.

## Access & Fraud Control
- **Separation of Duties**: Logic enforces that the person who *creates* a vendor bill cannot be the same person who *approves* the payment.
- **MFA (Multi-Factor Authentication)**: Mandatory for all users with access to bank details or payment execution.
- **IP Restrictions**: Administrative access is restricted to the corporate VPN.

## Audit Resilience
- **Shadow Logging**: Every read and write to the ledger is logged to an independent, tamper-proof external server.
- **SOC 1 Type II Compliance**: The system is designed to meet the rigorous standards for financial reporting controls.

---
[← Previous: Technology Stack](10-tech-stack.md) | [Back to Index](README.md) | [Next: Deployment Strategy →](12-deployment.md)
