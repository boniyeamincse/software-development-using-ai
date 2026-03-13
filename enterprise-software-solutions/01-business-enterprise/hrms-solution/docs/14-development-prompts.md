# 14 - HRMS Solution Development Prompts

## Employee Lifecycle & Records
### Prompt 1: Centralized Employee Profile Hub
"Design a PostgreSQL schema for a comprehensive employee profile system. Support versioned history for job titles, departments, and compensation. Implement a secure 'Document Vault' for storing digital copies of contracts, certifications, and identification documents with automated expiry alerts."

### Prompt 2: Intelligent Onboarding Workflow
"Develop a state-machine based onboarding engine. When a new hire is added, the engine should automatically trigger tasks for IT (Hardware provisioning), HR (Background check), and Finance (Payroll setup). Include a 'Progress Tracker' for the manager and the new hire."

## Time, Attendance & Leaves
### Prompt 3: Global Leave Management Service
"Implement a flexible leave management service that handles diverse leave types (Casual, Medical, Parental, Sabbatical). Support 'Accrual Logic' where leave balances increase monthly based on tenure and 'Carry-forward' rules for the new financial year."

### Prompt 4: Geofenced Attendance & Shift Tracking
"Create a mobile-first attendance service. Support Clock-in/Clock-out with GPS verification and photo evidence (to prevent 'Buddy Punching'). Implement a 'Shift Scheduler' that identifies coverage gaps and sends automated 'Shift Swap' notifications to eligible employees."

## Performance & Growth
### Prompt 5: 360-Degree Feedback & Review Hub
"Design an architecture for a 360-degree performance review system. Support feedback from Peers, Direct Reports, and Managers. Implement a 'Sentiment Analysis' layer to flag overly critical or biased reviews and provide a summary dashboard for HR."

### Prompt 6: Learning Management System (LMS) Bridge
"Develop an integration module that links employee performance goals to specific training courses. If an employee is marked for 'Leadership Development', the system should automatically recommend and track progress through relevant internal or external courses."

## Trust, Privacy & Finance
### Prompt 7: Global Payroll & Compliance Engine
"Design a payroll service that handles multi-currency payments and regional tax deductions (e.g., 401k, Pension, Social Security). Integrate with an external payment provider (like Wise or local banks) and generate secure, encrypted digital paystubs."

### Prompt 8: CCPA/GDPR 'Right to be Forgotten' Handler
"Implement a secure workflow for processing employee 'Data Deletion' requests post-resignation. ensure that all PII (Personally Identifiable Information) is purged from active databases and backups while maintaining anonymized records for historical financial reporting."

## Analytics & specialized Features
### Prompt 9: Employee Engagement & Churn Predictor
"Create a data visualization dashboard tracking 'Employee Turnover Rate', 'Average Tenure', and 'Departmental Happiness' (via periodic pulse surveys). Use a machine learning model to identify employees at high-risk of leaving."

### Prompt 10: AI-Powered Talent Matcher
"Develop a recommendation engine for internal mobility. When a new job opening is created within the company, use vector search (e.g., pgvector) to match the job requirements against the skills and experiences of current employees for potential promotions."

---
[← Previous: Roadmap & Future Enhancements](13-future-features.md) | [Back to Index](README.md) | [Next: Task Status →](15-task-status.md)
