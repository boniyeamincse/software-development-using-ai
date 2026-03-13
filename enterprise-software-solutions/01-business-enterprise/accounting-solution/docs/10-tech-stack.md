# 10 - Accounting Technology Stack

## Core Engineering
- **Backend API**: Java (Spring Boot) or Go (Golang).
- **Frontend**: Next.js (React) with high-performance data grids (AG Grid or custom).
- **Automation**: Celery or Temporal for background reconciliation workers.

## Financial & Integrity
- **Primary Database**: PostgreSQL (configured with serializable isolation).
- **Ledger Security**: Immutable, hashing-based integrity checks for entry sequences.
- **Integration**: Plaid/Yodlee (Banking) & Avalara (Tax).

## Infrastructure
- **Hosting**: AWS with VPC isolation and dedicated hardware instances for core databases.
- **Security**: AWS CloudHSM for managing financial encryption keys.
- **Logging**: Immutable audit logs exported to an external security cluster.

---
[← Previous: System Workflows](09-workflow.md) | [Back to Index](README.md) | [Next: Security & Compliance →](11-security.md)
