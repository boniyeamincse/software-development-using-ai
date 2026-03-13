# 14 - Hospital Management Solution Development Prompts

## Clinical & Patient Management
### Prompt 1: High-Fidelity Electronic Health Record (EHR) Schema
"Design a PostgreSQL schema for a comprehensive EHR system. Support 'Encounter-based' records, multiple diagnoses (ICD-10), and 'Clinical Note' versioning. ensure sensitive data is stored using 'Encryption at Rest' and 'Field-Level Masking' for non-clinical staff."

### Prompt 2: Real-time Operating Theater (OT) Scheduler
"Develop a scheduling service for hospital operating theaters. The system must account for 'Surgeon Availability', 'Anesthesiologist Scheduling', and 'Post-Op Recovery Bed' capacity. Implement a 'Conflict Resolver' that flags overlapping surgeries in the same OT."

## Hospital Operations & Logistics
### Prompt 3: predictive Bed Management & Census Engine
"Create a data visualization service that tracks 'Bed Occupancy' in real-time. Use a machine learning model to predict 'Admissions' and 'Discharges' based on historical trends to help the hospital manage surge capacity and reduce 'Boarding' in the ER."

### Prompt 4: Strategic Pharmacy & Inventory Orchestrator
"Implement a medication management system that tracks 'Unit-Dose' inventory levels. Support 'Expiration Alerts', 'Low-Stock Triggers', and 'Automated Fulfillment' requests to vendors. integrate with a barcode scanner for 'Three-way Match' (Patient, Medication, Dose)."

## Interaction & Telehealth
### Prompt 5: Omni-channel Patient Communication Hub
"Design an architecture that aggregates communications from Patient Portals, Email, and SMS. every interaction must be linked to a patient profile in a unified 'Timeline' view. Implement secure, HIPAA-compliant messaging for doctor-patient interaction."

### Prompt 6: AI-Driven Symptom Checker & Triage
"Develop a service that accepts patient-reported symptoms and uses an LLM (e.g., GPT-4) to provide a preliminary 'Triage Category' (Emergent, Urgent, Non-Urgent). Ensure the system provides a clear disclaimer that it is for 'decision support only' and not a diagnosis."

## Trust, Privacy & Compliance
### Prompt 7: HIPAA-Compliant Data Privacy Suite
"Implement a set of APIs for 'Access Log Review' and 'Data Export' as required by HIPAA/HITECH. The system must provide a permanent, immutable audit log of every user who has viewed a specific patient's PHI (Protected Health Information)."

### Prompt 8: centralized Medical Audit Transaction Vault
"Design a secure, write-once-read-many (WORM) audit log for all critical clinical and financial movements. Every medication order, surgical note, and billable event must be hashed and stored to ensure data integrity for medical malpractice audits."

## Analytics & specialized Features
### Prompt 9: Executive Revenue Cycle (RCM) Dashboard
"Create a data visualization dashboard tracking 'Net Patient Revenue', 'Days in Accounts Receivable' (DAR), and 'Claim Denial Rate'. Provide drill-down reports per department and insurance payer."

### Prompt 10: AI Next-Best-Action (NBA) for Care Coordination
"Develop a recommendation engine that suggests the 'Next Best Action' for a care coordinator based on the patient's discharge plan and historical success patterns (e.g., 'Recommend scheduling a follow-up appointment within 48 hours')."

---
[← Previous: Roadmap & Future Enhancements](13-future-features.md) | [Back to Index](README.md) | [Next: Task Status →](15-task-status.md)
