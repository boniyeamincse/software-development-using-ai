# 14 - Compliance Solution Development Prompts

## Regulatory & Policy Core
### Prompt 1: Dynamic Regulatory Framework Schema
"Design a PostgreSQL schema for managing diverse regulatory frameworks (e.g., GDPR, HIPAA, SOX, ISO 27001). Support 'Control Mapping' where a single company policy can satisfy requirements across multiple frameworks. Implement 'Version Control' for all policy documents."

### Prompt 2: automated Compliance Gap Analyzer
"Develop a service that compares 'Expected' control states with 'Actual' system configurations (imported via audit logs or cloud APIs). Generate a 'Gap Report' that identifies missing controls and provides a 'Risk Impact' score for each."

## Monitoring & Evidence
### Prompt 3: Immutable Evidence Vault
"Create an architecture for a secure Evidence Vault. Support uploads of screenshots, log files, and PDF reports. Every file must be hashed and time-stamped on a write-once-read-many (WORM) storage layer to ensure it is tamper-proof for external auditors."

### Prompt 4: Real-time Continuous Monitoring Hub
"Implement a background worker that periodically pulls security and configuration data from infrastructure providers (AWS, Azure, Google Cloud). Automatically flag 'Out-of-Compliance' events (e.g., Unencrypted buckets, Open SSH ports) and trigger an 'Incident Workflow'."

## Workflow & Task Management
### Prompt 5: Compliance Audit Lifecycle Engine
"Design a state-machine based workflow for managing internal and external audits. support roles like 'Auditor', 'Policy Owner', and 'Compliance Officer'. Automatically assign 'Remediation Tasks' to IT teams when a control failure is identified."

### Prompt 6: automated Vendor Risk Assessment (VRA)
"Develop a portal for conducting vendor security assessments. Support custom 'Questionnaires', automated 'Risk Scoring' based on answers, and a 'Vendor Scorecard' that tracks their compliance status over time."

## Trust, Privacy & Integrity
### Prompt 7: Global Data Privacy & Subject Access Suite
"Implement a set of APIs for managing 'Data Subject Access Requests' (DSAR). The system must facilitate the identification, review, and secure delivery of PII related to a requester, with an automated 'Disclosure Audit Log'."

### Prompt 8: centralized Policy Acceptance & Training Hub
"Create a service that tracks 'Employee Acceptance' of company policies. Automatically send reminders to employees who haven't reviewed new policies and integrate with an external LMS (Learning Management System) for compliance training verification."

## Analytics & specialized Features
### Prompt 9: Executive Compliance & Risk Dashboard
"Create a data visualization dashboard tracking 'Overall Compliance posture', 'Open Remediation Tasks', and 'Audit Readiness Score'. provide drill-down reports for different departments and geographic regions."

### Prompt 10: AI-Powered Regulatory Update Analyzer
"Develop an AI service that monitors official regulatory websites for updates. Use an LLM to summarize the changes and 'Predict' which internal policies and controls need to be updated to maintain compliance."

---
[← Previous: Roadmap & Future Enhancements](13-future-features.md) | [Back to Index](README.md) | [Next: Task Status →](15-task-status.md)
