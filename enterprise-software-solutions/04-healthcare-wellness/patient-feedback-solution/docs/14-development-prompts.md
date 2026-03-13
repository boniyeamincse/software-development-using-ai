# 14 - Patient Feedback Solution Development Prompts

## Capture & Interaction
### Prompt 1: Multi-Channel Feedback Intake Hub
"Design an architecture for a global patient feedback system. Support multiple capture methods: 'Post-Visit SMS', 'In-app Popups', 'Qr-code Clinic Surveys', and 'Email Follow-ups'. Implement a 'Conflict Resolver' logic that prevents over-surveying the same patient within a 30-day window."

### Prompt 2: Real-time Patient NPS & CSAT Engine
"Develop a service that calculates NPS (Net Promoter Score) and CSAT (Customer Satisfaction) in real-time as feedback is received. Automatically trigger an 'Alert' (via Email/Slack) to clinic managers for any 'Detractor' score (0-6) for immediate follow-up."

## Analysis & Insights
### Prompt 3: AI-Powered Sentiment & Topic Analysis
"Develop an AI service that analyzes patient comments. use an LLM (e.g., GPT-4) to provide a preliminary 'Sentiment Category' (Positive, Neutral, Negative) and identify 'Key Themes' (e.g., Long Wait Times, Professional Staff, Cleanliness). tag every feedback for easy filtering."

### Prompt 4: Integrated Service-Recovery Workflow
"Create a state-machine based workflow for managing 'Negative Feedback'. Automatically assign a 'Remediation Task' to the department head. Every action taken during the 'Service Recovery' process must be logged in an immutable audit trail."

## Trust, Privacy & Integrity
### Prompt 5: HIPAA-Compliant Privacy & Anonymity Vault
"Design a secure, write-once-read-many (WORM) audit log specifically for patient feedback. While individual comments may be shared with staff, the patient's identity (PHI) must be encrypted and masked. support 'Anonymization' options for patients who wish to remain private."

### Prompt 6: Immutable Data Integrity Vault
"Implement a robust 'Tamper-proof' vault for all raw feedback data. every submission must be hashed and stored to ensure data integrity for internal quality audits and external accreditation (like JCI or URAC) requirements."

## Integration & Reporting
### Prompt 7: Global Health Exchange (HIE) & EHR Bridge
"Design an integration API that syncs anonymized patient satisfaction scores with regional 'Health Information Exchanges' (HIE) and internal 'EHR' (Electronic Health Record) systems for a 360-degree patient view."

### Prompt 8: automated Performance Benchmarking Hub
"Develop a service that compares feedback results across different clinic locations and providers. Provide a 'Benchmark' against national healthcare standards and identifies 'High-Performing' teams for internal recognition."

## Analytics & specialized Features
### Prompt 9: Executive Patient Experience Dashboard
"Create a data visualization dashboard tracking 'Overall NPS Trend', 'Top Departmental Compliments', and 'Service Recovery Success Rate'. Provide drill-down reports per clinic, provider, and patient demographic."

### Prompt 10: AI-Powered 'Patient Attrition' Predictor
"Develop a machine learning model that analyzes feedback history and visit data. Predict the likely 'Churn Risk' for a patient (likelihood of not returning) and automatically trigger 'High-Priority' outreach from the patient experience team."

---
[← Previous: Roadmap & Future Enhancements](13-future-features.md) | [Back to Index](README.md) | [Next: Task Status →](15-task-status.md)
