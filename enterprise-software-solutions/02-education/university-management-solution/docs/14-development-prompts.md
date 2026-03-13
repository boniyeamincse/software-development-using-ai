# 14 - University Management Development Prompts

## Core System Architecture & Setup
### Prompt 1: Multi-Tenant Schema Design
"Design a highly scalable, multi-tenant PostgreSQL schema for an enterprise university management system. The schema must support multiple campuses, diverse grading systems (GPA, CGPA, Percentage), and complex faculty-student relationships. Include table definitions for `campuses`, `departments`, `programs`, `courses`, and `enrollments` with appropriate foreign keys and indexes for performance."

### Prompt 2: OAuth2 & RBAC Implementation
"Implement a robust OAuth2 and Role-Based Access Control (RBAC) system in Node.js (TypeScript). Define specific scopes for `Registrar`, `Dean`, `Faculty`, and `Student`. Ensure that faculty can only access grades for courses they are currently teaching, while students have read-only access to their own academic history."

## Academic Modules
### Prompt 3: Course Registration Logic
"Write a backend service to handle high-concurrency course registration during enrollment periods. Implement logic to check for prerequisites, avoid schedule conflicts (time/room), and enforce seat limits. Use database transactions to ensure consistency and prevent over-enrollment."

### Prompt 4: Dynamic Grading Engine
"Create a flexible grading engine that can be configured per department. The engine should support weighted components (e.g., 20% Midterm, 10% Quizzes, 20% Lab, 50% Final) and automatically calculate CGPA based on credit hours and grade points. Include error handling for incomplete grades."

## Research & Faculty Modules
### Prompt 5: Research Grant Tracking
"Develop a module for tracking research grants and publications. Include features for budget allocation, expense tracking, and approval workflows for grant-funded equipment purchases. Support document uploads for grant proposals and peer-reviewed papers."

### Prompt 6: Faculty Workload Calculator
"Implement a tool that calculates faculty workload based on teaching hours, research supervised, and administrative duties. Generate alerts if a faculty member's load exceeds university policy or if there are conflicts in their assigned teaching blocks."

## Student Services & Finance
### Prompt 7: Scholarship Eligibility Checker
"Build an automated system that checks student eligibility for various scholarships based on GPA, socio-economic status, and extracurricular achievements. Integrate with the finance module to automatically apply tuition waivers to eligible students' accounts."

### Prompt 8: Finance & Payment Gateway
"Integrate the university finance module with major payment gateways (Stripe, PayPal). Implement logic for late fee calculation, installment payment plans, and automatic generation of professional tax-ready tuition receipts."

## Reporting & Analytics
### Prompt 9: Enrollment Trend Analysis
"Create a data visualization service that analyzes enrollment trends over the last 5 years. Group data by program, gender, and geographic origin. Output the data in a format suitable for Chart.js or D3.js implementation on the executive dashboard."

### Prompt 10: Alumni Engagement Tracker
"Develop a system to track alumni career progression and donation history. Include a 'Mentorship Match' algorithm that pairs current students with alumni based on their field of study and career goals."
