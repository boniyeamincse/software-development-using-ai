# 14 - Telemedicine Solution Development Prompts

## virtual Care Core
### Prompt 1: High-Performance Video Consultation Hub
"Design an architecture for a real-time video consultation platform. use WebRTC for low-latency peer-to-peer communication and implement a 'TURN/STUN' server cluster for reliable connectivity. Support 'Session Recording' and 'Side-car Chat' within the video interface."

### Prompt 2: Secure Digital Prescription (eRx) Engine
"Develop a service that allows doctors to issue digital prescriptions during a video call. The system must integrate with a 'Medication Database' (like First Databank), automatically check for 'Drug-Drug Interactions', and generate a signed PDF with a secure QR code."

## Patient & Provider Workflow
### Prompt 3: Dynamic Triage & 'Waiting Room' Logic
"Create a backend service for a virtual waiting room. Implement 'Priority Triage' where emergency cases are moved to the top. Provide patients with a 'Real-time Wait Estimate' and support 'Automated Check-in' notifications for the provider."

### Prompt 4: Integrated medical Imaging Viewer
"Design an architecture for a web-based DICOM/imaging viewer. Allow patients to upload X-rays or MRIs before the call and ensure the provider can 'Synchronously Scroll' through the images with the patient during the consultation."

## Trust, Privacy & Integrity
### Prompt 5: HIPAA-Compliant Session Audit Vault
"Design a secure, write-once-read-many (WORM) audit log for all telemedicine sessions. Every call start/end, chat message, and prescription issue must be hashed and stored with the original rationale to ensure data integrity for medical audits."

### Prompt 6: Multi-Factor Authentication (MFA) for PHI
"Implement a robust MFA system specifically for accessing patient health records (PHI). Support 'TOTP' (Time-based One-time Password) and 'SMS/Email Verification' to ensure that only authorized clinicians can view sensitive data during a session."

## Integration & Finance
### Prompt 7: Global Health Exchange (HIE) Bridge
"Design an integration API that syncs consultation summaries and digital prescriptions with regional 'Health Information Exchanges' (HIE). Use FHIR (Fast Healthcare Interoperability Resources) standards for data exchange."

### Prompt 8: automated Medicare/Insurance Billing Hub
"Develop a billing service that converts virtual encounters into 'Coded Claims' specifically for telemedicine (e.g., using 'GT' or '95' modifiers). automatically check for 'Payer Eligibility' before a session is initiated."

## Analytics & specialized Features
### Prompt 9: Provider Utilization & Velocity Dashboard
"Create a data visualization dashboard tracking 'Daily Consultation Volume', 'Average Session Duration', and 'Patient Satisfaction Score'. provide 'Provider-to-Provider' comparison and identify 'Peak Demand' periods for staffing."

### Prompt 10: AI-Powered 'Sentiment' & Risk Hub
"Develop an AI service that analyzes anonymized text from consultation chats. Use an LLM to identify 'Patient Sentiment' and flag 'High-Risk' keywords (e.g., self-harm, severe allergies) for immediate medical supervision or intervention."

---
[← Previous: Roadmap & Future Enhancements](13-future-features.md) | [Back to Index](README.md) | [Next: Task Status →](15-task-status.md)
