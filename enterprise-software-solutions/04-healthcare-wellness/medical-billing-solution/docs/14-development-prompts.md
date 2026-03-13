# 14 - Medical Billing Solution Development Prompts

## Core billing & Claims
### Prompt 1: High-Performance Claim Adjudication Engine
"Design a PostgreSQL schema for a medical billing system. Support 'Electronic Claim Filing' (EDI 837), 'Status Tracking' (Submitted, Pending, Denied, Paid), and 'Reason Code' mapping. Implement a constraint that ensures a claim cannot be submitted without a valid NPI (National Provider Identifier) and ICD-10 code."

### Prompt 2: Real-time Insurance Eligibility Gateway
"Develop a service that integrates with a clearinghouse API (like Change Healthcare or Waystar) to verify patient insurance eligibility in real-time. The service should return specific details on 'Co-pay', 'Deductible Remaining', and 'Plan Status'."

## revenue Cycle Management (RCM)
### Prompt 3: automated Denial Management & Appeal Workflow
"Create a state-machine based workflow for managing denied claims. When a 'Denial' is received (EDI 835), automatically assign a 'Remediation Task' to the billing team based on the denial reason (e.g., Coding Error, Missing Info, Authorization). implement 'Appeal Template' generation."

### Prompt 4: Dynamic patient Statement & Payment Hub
"Develop a service that generates 'Patient Statements' by aggregating adjudicated claims and out-of-pocket costs. Support 'Online Payment Integration' (Stripe/PayPal) and automatically update the 'Patient Responsibility' balance once a payment is confirmed."

## Trust, Integrity & compliance
### Prompt 5: Immutable Financial Audit transaction Vault
"Design a secure, write-once-read-many (WORM) audit log for all financial movements in the billing system. every claim submission, payment posting, and adjustment must be hashed and stored with the original rationale to ensure compliance with medical auditing standards."

### Prompt 6: HIPAA-Compliant PHI encryption Hub
"Implement a robust 'Encryption at Rest' and 'Encryption in Transit' strategy for Protected Health Information (PHI). Ensure that all sensitive patient data (Name, DOB, SSN) is masked in the UI for anyone except authorized billing personnel with higher-tier permissions."

## Integration & Finance
### Prompt 7: Global Health Exchange (HIE) Bridge
"Design an integration API that pulls clinical encounter data directly from EHR systems (Electronic Health Records) using FHIR (Fast Healthcare Interoperability Resources). Support 'Automated Charge Capture' to reduce manual data entry errors."

### Prompt 8: centralized Bank Reconciliation Service
"Develop a service that matches 'EOB' (Explanation of Benefits) data from insurance carriers with internal bank deposit records. automatically flag 'Missing Payments' or 'Amount Mismatches' for the finance team's review."

## Analytics & specialized Features
### Prompt 9: Executive Revenue Cycle KPIs Dashboard
"Create a data visualization dashboard tracking 'Days in Accounts Receivable' (DAR), 'Clean Claim Rate', and 'Net Collection Ratio'. Provide drill-down reports per provider and insurance payer to identify high-denial trends."

### Prompt 10: AI-Powered 'Denial Prediction' Engine
"Develop a machine learning model that analyzes historical claim data. Predict the likely 'Denial Risk' for a new claim before it is submitted and provide 'Corrective Suggestions' to the billing team (e.g., 'Check Eligibility', 'Verify Modifier')."

---
[← Previous: Roadmap & Future Enhancements](13-future-features.md) | [Back to Index](README.md) | [Next: Task Status →](15-task-status.md)
