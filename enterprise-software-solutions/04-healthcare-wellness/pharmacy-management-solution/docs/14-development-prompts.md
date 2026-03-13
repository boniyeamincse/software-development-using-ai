# 14 - Pharmacy Management Solution Development Prompts

## prescription & Inventory Core
### Prompt 1: precision 'Unit-Dose' Inventory System
"Design a PostgreSQL schema for a pharmacy inventory system. Support 'Batch/Lot tracking', 'Expiration Date' monitoring, and 'Barcode Integration'. Implement a 'Reorder Trigger' service that automatically alerts suppliers when stock levels for a specific medication hit a critical threshold."

### Prompt 2: Real-time 'Drug-Drug Interaction' Checker
"Develop a service that accepts a list of medications and checks for potential 'Interactions' or 'Allergy Conflicts' against a patient's medical profile. integrate with an external medication database (like Medscape or First Databank) and Provide 'Warning Levels' (Mild, Moderate, Severe)."

## Dispensing & Workflow
### Prompt 3: digital Prescription (eRx) Intake & Verification
"Create a backend service for processing e-prescriptions received from medical systems. Implement a 'Verification Workflow' where a pharmacist must review and digitally sign the order before it can be filled. Support 'Insurance Eligibility' checks at the point of intake."

### Prompt 4: automated 'Three-Way Match' Dispensing
"Develop a dispensing workflow that uses barcode scanning. The system must verify that the 'Patient ID', 'Prescription ID', and 'Physical Medication Container' all match before the label can be printed. Log every successful and failed match for audit."

## Trust, Integrity & Finance
### Prompt 5: Immutable pharmacy Audit Vault (NARCO)
"Design a secure, write-once-read-many (WORM) audit log specifically for controlled substances. every transaction involving a 'Schedule II-V' drug must be hashed and stored to ensure a permanent, tamper-proof record for regulatory authorities (like the DEA)."

### Prompt 6: Insurance Adjudication & Billing Hub
"Implement a real-time 'Claims Adjudication' service. The system should send prescription data to a PBM (Pharmacy Benefit Manager) and receive an instant 'Approval' or 'Rejection' with the patient's exact out-of-pocket cost."

## Interaction & specialized Features
### Prompt 7: Omni-channel refill & Pickup Alerts
"Design an architecture that manages prescription refills. support 'Mobile App push', 'SMS Reminders', and 'Automated Voice Calls' to notify patients when their medication is ready for pickup or needs a new authorization from their doctor."

### Prompt 8: centralized Vaccine & Point-of-care Testing
"Create a module for managing pharmacy-based clinical services. Support 'Appointment Scheduling' for vaccines (Flu, COVID, etc.) and 'Results Reporting' for point-of-care tests (Glucose, Cholesterol). integrate with regional health registries."

## Analytics & specialized Features
### Prompt 9: Executive Pharmacy KPIs Dashboard
"Create a data visualization dashboard tracking 'Daily Fill Volume', 'Inventory Turnover Rate', and 'Average Wait Time per Prescription'. Provide drill-down reports per pharmacist and department."

### Prompt 10: AI-Powered 'Demand Forecasting'
"Develop a predictive model that analyzes historical sales and seasonal trends. Forecast the 'Medication Demand' for the next 30 days to optimize inventory orders and reduce the risk of stock-outs or expirations."

---
[← Previous: Roadmap & Future Enhancements](13-future-features.md) | [Back to Index](README.md) | [Next: Task Status →](15-task-status.md)
