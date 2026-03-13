# 14 - Scholarship Management Development Prompts

## Scholarship Lifecycle
### Prompt 1: Multi-Criteria Eligibility Engine
"Design a PostgreSQL schema and matching logic for a complex scholarship eligibility engine. THe system must support diverse criteria (GPA, Residency, Financial Need, Ethnicity, Program of Study). Implement a 'Weighted Scoring' system that ranks applicants based on multiple configured factors."

### Prompt 2: Blind Review Portal Architecture
"Implement an anonymous 'Blind Review' system where applicant names and PII are redacted for external reviewers. Design the API to serve 'Candidate IDs' instead of names and handle secure submission of review scores and qualitative feedback."

## Applications & Documents
### Prompt 3: Dynamic Application Form Builder
"Develop a React/TypeScript form builder that allows admin to create custom scholarship applications. Support conditional logic (e.g., 'If GPA < 3.5, show question X'). Ensure all form data is versioned and stored in a flexible JSONB column."

### Prompt 4: Secure Document Upload & OCR
"Create a secure document handling service for transcripts and income proof. Integrate with AWS Textract or similar to automatically extract key values (GPA, Total Income) from uploaded PDFs to pre-verify applicant claims."

## Selection & Workflow
### Prompt 5: Reviewer Assignment Algorithm
"Build an algorithm that automatically assigns scholarship applications to committee members based on their expertise and current workload. Ensure 'Conflict of Interest' checks (e.g., a reviewer cannot grade an applicant from their own department)."

### Prompt 6: Multi-Stage Approval Workflow
"Implement a state-machine based approval workflow for scholarship disbursement. The stages should include: Initial Screening, Committee Review, Financial Aid Verification, Dean's Final Sign-off. Use immutable logs to track every transition."

## Finance & Disbursement
### Prompt 7: SIS Financial Aid Bridge
"Develop an integration module that syncs awarded scholarships with the university's primary Student Information System (SIS). Handle partial disbursements, mid-year cancellations (e.g., if GPA drops), and automatic tuition balance updates."

### Prompt 8: Donor Reporting Dashboard
"Create a reporting tool for scholarship donors. Aggregate data showing the 'Total Impact' of their fund (number of students helped, average GPA of recipients, graduation rates). Provide exportable reports and a secure donor login."

## Communication & Engagement
### Prompt 9: Automated Notification Suite
"Develop a notification engine that manages scholarship status updates (Awarded, Waitlisted, Regret). Include high-quality template support for award letters and automated reminders for recipients to submit 'Thank You Letters' to donors."

### Prompt 10: Scholarship Renewal Checker
"Implement a background service that annually verifies if current scholarship recipients still meet the 'Renewal Criteria' (e.g., maintaining a specific GPA or staying enrolled in a specific program). Trigger alerts for students at risk of losing funding."

---
[← Previous: Roadmap & Future Enhancements](13-future-features.md) | [Back to Index](README.md) | [Next: Task Status →](15-task-status.md)
