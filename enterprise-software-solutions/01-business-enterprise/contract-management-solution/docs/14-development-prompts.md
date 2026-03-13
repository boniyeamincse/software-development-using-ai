# 14 - Contract Management Solution Development Prompts

## Authoring & Lifecycle
### Prompt 1: Dynamic Clause & Template Engine
"Design a PostgreSQL schema for a contract management system. Support 'Clause Libraries' that can be used across multiple contract templates. Implement version control for templates and support 'Variable Injection' (e.g., {{contract_value}}, {{effective_date}}) into generated documents."

### Prompt 2: Integrated Rich-Text Contract Editor
"Develop a React component for authoring contracts. Support 'Track Changes', 'Inline Commenting', and 'Clause Suggestion' from the library. Implement a 'Comparison Engine' that highlights differences between contract versions (Redlining)."

## Workflow & Collaboration
### Prompt 3: multi-Stage Approval & Negotiation Hub
"Create a state-machine based workflow for contract negotiations. Support roles like 'Legal Reviewer', 'Finance Approver', and 'External Signatory'. Implement 'Lock Mode' when a contract is sent for external review to prevent internal changes."

### Prompt 4: Real-time Negotiation Timeline
"Develop a service that records every interaction (Comment, Version Upload, Approval) in a unified 'Negotiation Timeline'. Use WebSockets to provide real-time updates to all internal parties when the external party uploads a new version."

## Execution & Signature
### Prompt 5: Electronic Signature Integration Hub
"Design an architecture for integrating with e-signature providers (e.g., DocuSign, HelloSign). Automatically trigger an 'Execution Workflow' once all internal approvals are complete and monitor the signing status in real-time."

### Prompt 6: Immutable Signed Document Vault
"Develop a secure Document Vault for finalized contracts. every executed contract and its 'Audit Certificate' must be hashed and stored on a write-once-read-many (WORM) storage layer to ensure it remains tamper-proof for the life of the agreement."

## Post-Execution & Integrity
### Prompt 7: Milestone & Obligation Tracker
"Implement a service that extracts 'Milestones' and 'Payment Due Dates' from finalized contracts. Automatically create 'Reminders' and 'Tasks' for the relevant stakeholders to ensure contractual obligations are met."

### Prompt 8: automated Contract Renewal Alerts
"Design a notification engine that identifies contracts approaching their 'Expiry Date'. Automatically trigger 'Renewal Workflows' or 'Termination Notices' based on the contract's specific 'Renewal Clauses' (e.g., 90-day notice period)."

## Analytics & specialized Features
### Prompt 9: Executive Contract Portfolio Dashboard
"Create a data visualization dashboard tracking 'Total Contract Value' (TCV), 'Average Negotiation Time', and 'Obligation Compliance Rate'. Provide drill-down reports per department and counterparty."

### Prompt 10: AI-Powered Clause Risk Analyzer
"Develop an AI service that analyzes uploaded contracts (PDF/Word). Use an LLM to identify 'High-Risk Clauses' (e.g., unfavorable termination rights, broad indemnification) and recommend 'Standardized Alternatives' from the clause library."

---
[← Previous: Roadmap & Future Enhancements](13-future-features.md) | [Back to Index](README.md) | [Next: Task Status →](15-task-status.md)
