# 14 - Clinic Management Solution Development Prompts

## Patient & Practice Orchestration
### Prompt 1: High-Performance Clinic Scheduler
"Design a PostgreSQL schema for a multi-specialty clinic scheduler. Support 'Recurring Appointments', 'Wait-listing', and 'Telehealth-only' slots. Implement a 'Conflict Resolver' logic that prevents double-booking a provider across different clinic locations."

### Prompt 2: Patient Registration & Digital Intake
"Develop a Node.js service for digital patient onboarding. The service should generate a secure, temporary link for patients to fill out 'Medical History', 'Consent Forms', and 'Insurance Data'. Automatically parse and validate insurance IDs using an external verification API."

## Clinical & Workflow
### Prompt 3: Dynamic SOAP Note Template Engine
"Create a React component for clinical documentation using the SOAP (Subjective, Objective, Assessment, Plan) format. Support 'Smart-Phrases' (autocompleting common medical text) and 'Template Switching' based on the appointment type (e.g., Wellness Check vs. Urgent Care)."

### Prompt 4: Integrated Lab & Imaging Request Tool
"Design an architecture for an integrated lab ordering system. Allow providers to select from a 'Standard Test Menu', automatically generate 'HL7/FHIR' messages for external labs, and support 'Push Notifications' when results are ready for review."

## Trust, Privacy & Finance
### Prompt 5: HIPAA-Compliant PHI Access Audit log
"Design a secure, write-once-read-many (WORM) audit log for all Protected Health Information (PHI) access. Every time a patient's chart is opened or edited, a permanent record of the User ID, Timestamp, and Action must be hashed and stored."

### Prompt 6: automated Medical Billing & Claim Hub
"Implement a billing service that converts clinical encounters into 'ICD-10/CPT' coded claims. Support 'Electronic Remittance Advice' (ERA) processing to automatically update payment status when an insurance carrier pays a claim."

## Interaction & specialized Features
### Prompt 7: Omni-channel Patient Communication Bridge
"Design an architecture that aggregates communications from Patient Portals, Email, and SMS. every interaction must be linked to a patient profile in a unified 'Timeline' view. Implement secure messaging for appointment reminders and follow-up instructions."

### Prompt 8: centralized Vaccine & Immunization Tracker
"Create a service that tracks patient immunization history and 'Upcoming Due Dates'. Support automated 'Reminder Notifications' for multi-dose vaccine series (e.g., Pediatric schedule) and integrate with regional 'Health Exchange' APIs."

## Analytics & specialized Features
### Prompt 9: Clinic Performance & Revenue Dashboard
"Create a data visualization dashboard tracking 'Patient Volume', 'Average Wait Time', and 'Revenue per Provider'. Provide drill-down reports per department and identify 'No-Show' trends for targeted follow-up campaigns."

### Prompt 10: AI-Powered 'No-Show' Predictor
"Develop a forecasting model that analyzes historical appointment data. Predict the likely 'No-Show Risk' for an upcoming appointment and automatically trigger 'High-Priority' reminders or suggestion for a 'Telehealth' switch."

---
[← Previous: Roadmap & Future Enhancements](13-future-features.md) | [Back to Index](README.md) | [Next: Task Status →](15-task-status.md)
