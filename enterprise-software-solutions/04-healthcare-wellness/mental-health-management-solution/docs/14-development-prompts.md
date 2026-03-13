# 14 - Mental Health Management Solution Development Prompts

## Core clinical & Privacy
### Prompt 1: High-Security clinical Session Schema
"Design a PostgreSQL schema for a mental health platform. Support 'Session Notes' (SOAP format), 'Patient Histories', and 'Clinical Assessments' (PHQ-9, GAD-7). every note must be encrypted with a unique key per provider/patient to ensure maximum privacy."

### Prompt 2: HIPAA-Compliant Video & Chat Orchestrator
"Develop an architecture for an integrated video and secure messaging service. Implement 'End-to-End Encryption' for all communications and ensure that session metadata (start/end times) is stored in an immutable audit vault for compliance."

## Interaction & Engagement
### Prompt 3: Dynamic 'Mood & Thought' Journal
"Create a React component for a student/patient 'Daily Journal'. Support 'Mood Tracking', 'Thought Diarization', and 'Integrative Goal Setting'. implement a 'Sentiment Analyzer' that flags 'Crisis Keywords' for immediate clinical supervision."

### Prompt 4: Integrated Self-Care Content library
"Design an architecture for a curated library of mental health resources (CBT exercises, Breathing techniques, Articles). support 'Content tagging' by condition and implement an 'AI Recommender' that suggests content based on the user's latest 'Clinical Assessment'."

## operations & Facility
### Prompt 5: Omni-channel Booking & Therapist Hub
"Develop a communication service for interaction between 'Therapists' and 'Patients'. Implement 'Secure Messaging', 'Virtual Appointment Scheduling', and 'Provider Availability' tracking. every interaction must be linked to the patient's 'Care Plan' in a unified timeline."

### Prompt 6: AI-Powered 'Intervention' Nudge Recommender
"Develop an AI service that analyzes a patient's journal and assessment data. Use an LLM or NLP model to provide daily 'Nudges' and 'Therapeutic Suggestions' (e.g., 'You've reported high anxiety today, how about trying this 5-minute Grounding exercise?')."

## Trust, Privacy & Finance
### Prompt 7: Ultra-Secure PHI & clinical Note Vault (WORM)
"Implement a robust 'Privacy Policy Engine' specifically for mental health data. Ensure that only authorized clinicians can see 'Clinical Notes' while admin staff only see 'Billing and Scheduling' records. Implement a secure audit log for every access event."

### Prompt 8: centralized Billing & Insurance transaction Vault
"Design a secure, write-once-read-many (WORM) audit log for all financial movements. Every session billing, insurance claim submission, and payment must be hashed and stored to ensure data integrity for medical audits."

## Analytics & specialized Features
### Prompt 9: Clinic Health & Patient Recovery Dashboard
"Create a data visualization dashboard tracking 'Overall Patient Progress' (aggregate PHQ/GAD scores), 'Clinic Utilization Rate', and 'Average Session Duration'. provide 'Month-over-Month' comparisons and identify 'High-Impact' treatment pathways."

### Prompt 10: AI-Powered 'Crisis Risk' Predictor
"Develop a predictive model that analyzes historical journal and assessment data. Predict the likely 'Crisis Risk' for a patient and automatically trigger 'Immediate Outreach' protocols or secondary clinical reviews."

---
[← Previous: Roadmap & Future Enhancements](13-future-features.md) | [Back to Index](README.md) | [Next: Task Status →](15-task-status.md)
