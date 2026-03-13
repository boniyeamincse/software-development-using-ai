# 05 - Medical Billing System Architecture

## Robust Transactional & High-Concurrency Design
The Medical Billing Solution utilizes a **State-Machine Driven Architecture** to track the complex lifecycle of every individual claim line-item.

## Technical Infrastructure
- **Core Engine**: Java (Spring Boot) or .NET for high-fidelity transactional processing and EDI parsing.
- **Frontend**: Next.js (React) optimized for data-heavy administrative tables and dashboards.
- **EDI Parser**: Specialized library for generating/processing X12 (837/835/270/271) healthcare files.
- **Task Orchestration**: Workflow engine (e.g., Temporal or Camunda) to manage the long-running claim lifecycle.

## Data & Reliability Strategy
- **Master Database (Azure SQL / AWS Aurora)**: High-availability relational DB with strict ACID compliance.
- **Audit Vault (WORM Storage)**: Immutable storage for all raw EDI files sent and received.
- **Integration Layer**: Secure VPN or dedicated tunnels for direct clearinghouse connectivity.
- **Identity**: Azure AD or Okta with RBAC and session auditing.

---
[← Previous: User Roles & Permissions](04-user-roles.md) | [Back to Index](README.md) | [Next: Database Design →](06-database-design.md)
