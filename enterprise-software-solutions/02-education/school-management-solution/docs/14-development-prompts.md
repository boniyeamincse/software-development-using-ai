# School Management System - Development Prompts (AI-Assisted Development)

This document contains 100 AI development prompts for building and improving the School Management System.

---

## Category 1: Student Management Module (Prompts 1-10)

### 1. Student Registration Feature
**Prompt**: You are a senior full-stack developer. Design and implement a comprehensive student registration module for a school management system. Include form validation (email uniqueness, roll number, DOB), auto-generation of student ID, and automatic user account creation with temporary password generation. Ensure GDPR compliance and implement proper error handling.

### 2. Student Profile Management
**Prompt**: Create a student profile page with the following sections: personal information, contact details, emergency contacts, document uploads, photo management, and address information. Implement role-based visibility (student sees limited info, admin sees all, teacher sees only assigned class students). Include edit functionality with audit logging of all changes.

### 3. Bulk Student Import
**Prompt**: Design a CSV import feature for bulk student registration. Handle duplicate detection, validation errors, missing required fields, and provide a detailed report showing successful imports and failures. Implement transaction rollback on critical errors and allow retry with corrected data.

### 4. Student Search & Filter
**Prompt**: Implement an advanced search and filter system for student management with the following features: search by name, email, roll number, phone; filter by class, section, status, enrollment date; multi-criteria filtering; and pagination with customizable page size.

### 5. Student Status Management
**Prompt**: Create a module to manage student statuses (Active, Inactive, Withdrawn, Transferred). Include state transition rules, approval workflows, notification to parents/teachers, and archival of inactive student data. Implement proper cascading effects on related records.

### 6. Student Academic History
**Prompt**: Design a feature to view and manage student academic history including class progression, subjects taken, exam results, and performance trends. Include visual representations (graphs, charts) and export functionality for transcripts.

### 7. Student Emergency Contacts
**Prompt**: Implement emergency contact management allowing students/parents to maintain multiple emergency contacts with relationship information, priority levels, and notification preferences. Ensure secure storage and controlled access.

### 8. Student Document Management
**Prompt**: Create a document management system for students to upload certificates, admission forms, birth certificates, identity proofs, and medical records. Implement document categorization, versioning, secure storage, virus scanning, and expiry tracking.

### 9. Student Communication Preferences
**Prompt**: Design a notification preferences system allowing students and parents to customize communication methods (email, SMS, in-app), frequency, and types of notifications they want to receive.

### 10. Student Analytics Dashboard
**Prompt**: Create a personalized dashboard for students showing attendance percentage, exam schedule, recent results, fee status, class announcements, and progress tracking. Include notifications for important events and deadlines.

---

## Category 2: Teacher Management Module (Prompts 11-20)

### 11. Teacher Registration & Onboarding
**Prompt**: Design a comprehensive teacher onboarding process including profile creation, credential verification, qualification uploads, subject specialization definition, class assignment, and orientation checklist tracking. Include automated welcome emails and credential validation.

### 12. Teacher Subject Assignment
**Prompt**: Implement a module to assign teachers to subjects and classes with semester/year-wise tracking. Include conflict detection (preventing double assignments), optimization for balanced workload, and automated notification to teachers of new assignments.

### 13. Teacher Schedule Management
**Prompt**: Create a scheduling system for teachers showing daily timetables, class schedules, office hours, free periods, and holiday information. Implement conflict detection and allow substitution request management.

### 14. Teacher Performance Metrics
**Prompt**: Design a performance tracking system monitoring key metrics: classes taught, attendance regularity, exam result quality, student feedback scores, assignment submission rates, and class performance trends. Implement visual analytics and comparative analysis.

### 15. Teacher Credential Verification
**Prompt**: Create a system to store, verify, and track teacher qualifications (degrees, certifications, training), with expiry date monitoring, renewal reminders, and compliance documentation. Include approval workflow and archival.

### 16. Teacher Absence Management
**Prompt**: Implement leave management for teachers with leave type categorization, approval workflows, substitute teacher assignment, and automatic notification to affected students/parents. Track leave balance and provide reports.

### 17. Teacher Communication Module
**Prompt**: Design an internal communication system for teachers to share class updates, announcements, and collaborate on curriculum. Include message threads, file attachments, read receipts, and archival functionality.

### 18. Teacher Evaluation System
**Prompt**: Create a peer evaluation and self-evaluation system for teachers with customizable evaluation criteria, scoring rubrics, feedback mechanisms, and performance improvement plans. Include confidentiality protections and appeals process.

### 19. Teacher-Parent Communication
**Prompt**: Implement a dedicated communication channel for teachers to contact parents regarding student progress, issues, or positive feedback. Include scheduling for parent-teacher meetings and automated reminders.

### 20. Teacher Dashboard & Analytics
**Prompt**: Design a comprehensive teacher dashboard showing assigned classes, attendance to mark, marks to enter, pending evaluations, communication messages, and professional development opportunities. Include quick-access action items.

---

## Category 3: Attendance System (Prompts 21-30)

### 21. Daily Attendance Marking
**Prompt**: Create an intuitive interface for teachers to mark daily attendance with quick actions (mark all present, bulk operations), leave management, remarks capability, and automatic parent notifications for absences. Include offline functionality with sync capability.

### 22. Attendance Percentage Calculation
**Prompt**: Implement automatic calculation of attendance percentage considering present, absent, leave, and late statuses. Create configurable rules for converting late arrivals, holidays vs. non-working days, and various attendance categories.

### 23. Attendance Reports
**Prompt**: Design comprehensive attendance reports including: student-wise attendance, class-wise attendance, monthly trends, defaulter lists, leave patterns, and exemption analysis. Include export functionality and visualization.

### 24. Attendance-Based Eligibility
**Prompt**: Create a system to flag students not meeting attendance eligibility requirements for exam participation or result publication. Implement configurable threshold (e.g., 75% attendance), exemption mechanisms, and notification workflows.

### 25. Parent Notification for Absence
**Prompt**: Implement automated SMS/email notifications to parents when their child is marked absent. Include notification scheduling, customization options, and ability for parents to acknowledge/respond to notifications.

### 26. Attendance Leave Management
**Prompt**: Design a leave request and approval system allowing students/parents to request leave with reason, admin approval workflow, automatic attendance marking, and leave balance tracking.

### 27. Attendance Analytics & Insights
**Prompt**: Create analytics showing attendance trends, patterns (e.g., Friday absences), student groups with low attendance, seasonal variations, and predictive models for potential absenteeism.

### 28. Attendance Correction Workflow
**Prompt**: Implement a process to correct erroneous attendance records with reason tracking, authority approval (admin/principal), audit trail, and automatic percentage recalculation.

### 29. Period-wise Attendance
**Prompt**: Design a system to mark attendance for individual class periods rather than just daily attendance, useful for colleges/upper classes. Track period attendance, calculate per-class percentages, and identify patterns.

### 30. Biometric Attendance Integration
**Prompt**: Design integration with biometric attendance systems (fingerprint, face recognition) including device connectivity, real-time sync, fallback mechanisms, and data reconciliation with manual entries.

---

## Category 4: Examination & Results (Prompts 31-50)

### 31. Exam Schedule Management
**Prompt**: Create a comprehensive exam scheduling system including exam creation, date/time scheduling, conflict detection, exam center assignment, duration configuration, and automatic clash prevention for multi-subject exams.

### 32. Admit Card Generation
**Prompt**: Design an automated admit card generation system with student details, exam information, center assignment, seat number, instructions, and printable/downloadable format. Include customizable templates.

### 33. Marks Entry Interface
**Prompt**: Create an efficient marks entry system for teachers allowing bulk mark input, formula-based calculations (percentage, grade), validation (marks within range), autosave, and batch submission with approval workflow.

### 34. Grade Configuration & Calculation
**Prompt**: Design a flexible grade calculation system supporting multiple grading scales (A-F, percentage-based, point-based), configurable cutoffs, grace marks, and automatic grade assignment based on percentage or marks.

### 35. Result Publication Workflow
**Prompt**: Implement a multi-step result publication process: mark entry → validation → teacher approval → admin review → principal approval → publication. Include stakeholder notifications at each step.

### 36. Result Slip Generation
**Prompt**: Create automated result slip generation with school header, student details, subject-wise marks and grades, total percentage, overall grade, position/rank, and formatted printing. Include digital storage and download capability.

### 37. Academic Transcript Generation
**Prompt**: Design a system to generate official academic transcripts showing multi-year academic performance, cumulative grades, achievements, and compliance with document standards. Include authentication features.

### 38. Performance Analytics
**Prompt**: Create analytics showing class performance, subject-wise performance, top/bottom performers, fail analysis, pass percentage trends, and comparative analysis with previous years. Include visualization tools.

### 39. Student Performance Tracking
**Prompt**: Implement a module to track individual student performance across exams, identify trends, strengths, weaknesses, and generate personalized performance reports for students and parents.

### 40. Exam Result Correction
**Prompt**: Design a correction mechanism for erroneous result entries with reason documentation, multi-level approval, automatic recalculation of dependent records, and audit trail. Prevent unauthorized corrections.

### 41. Class Ranking & Position
**Prompt**: Create an automated system to calculate student rankings within a class based on exam performance. Include tie-breaking rules, distinction criteria, and rank publication controls.

### 42. Result Statistics & Graphs
**Prompt**: Design visualization tools showing result distribution (histograms), trend analysis (line graphs), subject performance (bar charts), and comparison matrices. Include data export capability.

### 43. Online Examination System
**Prompt**: Design an online exam platform with timed question delivery, shuffle capability, auto-submit after time, progress tracking, answer saving, and automatic grading for objective questions. Include session security and attempt logging.

### 44. Question Bank Management
**Prompt**: Create a question bank system with categorized questions, difficulty levels, Bloom's taxonomy mapping, and exam paper auto-generation. Include duplicate detection and usage analytics.

### 45. Subjective Answer Evaluation
**Prompt**: Design a workflow for evaluating subjective exam answers including answer sheets, rubric-based marking, comment management, moderation process, and dispute resolution for remarking requests.

### 46. Exam Center Management
**Prompt**: Implement exam center configuration including capacity definition, invigilator assignment, room allocation, seating arrangement generation, and center-specific instructions.

### 47. Invigilator Management
**Prompt**: Create a system for invigilator management including qualification verification, assignment to exams, duty schedule, incident reporting, and performance evaluation.

### 48. Exam Analytics & Insights
**Prompt**: Design analytics showing exam-wise performance, question difficulty analysis, answer pattern analysis, and student performance by skill category. Include reports for curriculum improvement.

### 49. Duplicate Question Detection
**Prompt**: Implement a system to detect duplicate or similar questions in question banks using string matching, semantic similarity, and manual review workflows.

### 50. Result Import & Export
**Prompt**: Create functionality to import exam results from external sources (Excel templates, other systems) with validation, and export results in various formats (Excel, CSV, XML) for integration with other systems.

---

## Category 5: Fee Management (Prompts 51-70)

### 51. Fee Structure Creation
**Prompt**: Design a fee structure definition system supporting multiple fee components (tuition, lab, sports, etc.), class-wise variations, category-specific charges, and annual updates. Include approval workflow.

### 52. Student Fee Assignment
**Prompt**: Create automatic fee assignment to students based on class enrollment with support for overrides, waivers, scholarships, and manual adjustments. Include effective date management.

### 53. Payment Processing
**Prompt**: Implement payment recording functionality supporting multiple payment methods (cash, check, credit card, bank transfer), automatic receipt generation, payment confirmation, and reconciliation with accounting system.

### 54. Invoice Generation & Email
**Prompt**: Design automated invoice generation with customizable templates, itemized charges, payment schedule, due dates, and email distribution to students/parents with calendar reminders.

### 55. Fee Reminders & Notifications
**Prompt**: Create a scheduled notification system sending payment reminders before due dates (-30, -15, -7, -1 days) via SMS/email, with customizable templates and escalation for overdue payments.

### 56. Discount & Concession Management
**Prompt**: Implement discount management supporting percentage-based or fixed discounts, category-based concessions (merit, need-based), approval workflows, and audit trail of all discounts applied.

### 57. Refund Processing
**Prompt**: Design a refund system identifying refund eligibility, initiating refund requests, multi-level approval, payment reversal, automatic reconciliation, and refund tracking with status updates.

### 58. Outstanding Dues Tracking
**Prompt**: Create a system tracking outstanding fee amounts per student, overdue status with aging analysis, late fees (if applicable), and automated escalation for long overdue amounts.

### 59. Fee Collection Reports
**Prompt**: Design comprehensive fee collection reports showing daily collection, collection by payment method, class-wise collection, payment status distribution, and trend analysis over time.

### 60. Fee Defaulters Management
**Prompt**: Implement tracking and management of students with outstanding fees including list generation, communication workflows, result/exam blocking rules, and escalation to parents/principal.

### 61. Payment Gateway Integration
**Prompt**: Implement payment gateway integration (Stripe, PayPal, local) supporting online fee payment, transaction handling, security (PCI compliance), and automatic reconciliation of payments.

### 62. Fee Exemption & Waivers
**Prompt**: Design a system for fee exemptions and waivers with category definition (scholarship, need-based, merit), eligibility criteria, approval workflow, and duration management.

### 63. Fee Structure Hierarchy
**Prompt**: Create support for complex fee structures including base fees, additional charges, variable components, and category-based variations. Include version management for historical tracking.

### 64. Accounting Integration
**Prompt**: Design integration with accounting systems for automatic journal entry creation, account reconciliation, financial reporting, and compliance with accounting standards.

### 65. Financial Dashboard
**Prompt**: Create a financial dashboard showing KPIs: total collection, outstanding amount, collection trend, payment method breakdown, and comparative analysis with previous periods.

### 66. Fee Payment History
**Prompt**: Implement detailed payment history tracking showing all transactions per student, payment dates, amounts, methods, and receipt availability for download/print.

### 67. Tax Invoice Generation
**Prompt**: Design tax-compliant invoice generation supporting GST/VAT calculations, tax registration details, invoice numbering, and export for accounting compliance.

### 68. Payment Reconciliation
**Prompt**: Create an automated reconciliation process matching bank deposits with recorded payments, flagging discrepancies, and auto-correction of minor mismatches.

### 69. Fee Adjustment & Credits
**Prompt**: Implement system for fee adjustments (increase/decrease), credit application (from overpayment or advance), and reversal of adjustments with proper documentation.

### 70. Late Fee & Penalties
**Prompt**: Design a configurable late fee system applying penalties after due date, escalating charges for extended delays, and exemption management based on reasons.

---

## Category 6: Notifications & Communication (Prompts 71-80)

### 71. In-App Notification System
**Prompt**: Design an in-app notification system with notification center, read/unread status, notification grouping by type, archival, and customizable notification preferences per user.

### 72. Email Notification Service
**Prompt**: Implement email notifications using templates, scheduled delivery, retry logic for failures, tracking of delivery status, and bounce handling. Integrate with SendGrid or similar service.

### 73. SMS Notification Service
**Prompt**: Design SMS notification functionality supporting message templating, character limit handling, delivery confirmation, cost tracking, and integration with SMS gateway provider (Twilio, etc.).

### 74. Push Notifications
**Prompt**: Implement push notifications for mobile apps using Firebase Cloud Messaging, including topic-based subscriptions, notification scheduling, and delivery analytics.

### 75. Notification Templates
**Prompt**: Create a notification template management system allowing creation of notification templates with variables, preview functionality, multi-language support, and reusability across modules.

### 76. Notification Scheduling
**Prompt**: Design scheduled notification sending with date/time scheduling, recurring notifications, timezone handling, and ability to cancel scheduled notifications.

### 77. Bulk Notifications
**Prompt**: Implement bulk notification sending to specific user groups (all parents, class 10 students, etc.) with recipient filtering and delivery tracking.

### 78. Announcement Management
**Prompt**: Create an announcement system allowing admins to post school-wide announcements, target specific groups, pin important announcements, and track viewing statistics.

### 79. Notification Preference Management
**Prompt**: Design a system allowing users to customize notification preferences: which notifications to receive, delivery methods preferred, quiet hours, and frequency limits.

### 80. Notification Analytics
**Prompt**: Implement analytics tracking notification delivery rates, open rates, click-through rates, and effectiveness metrics. Include reporting for optimization.

---

## Category 7: Security & Admin (Prompts 81-90)

### 81. Role-Based Access Control
**Prompt**: Design and implement comprehensive RBAC with roles (Super Admin, Admin, Teacher, Student, Parent, Accountant), permission definition, role assignment, and permission enforcement at API level with audit logging.

### 82. Two-Factor Authentication
**Prompt**: Implement 2FA using TOTP (Google Authenticator), SMS, or email with backup codes, recovery mechanisms, and enforcement policies for admin users.

### 83. Audit Logging System
**Prompt**: Design comprehensive audit logging capturing user actions (login, data modifications, permission changes), timestamp, IP address, user agent, and operation details. Ensure immutability and secure storage.

### 84. Data Encryption
**Prompt**: Implement encryption for sensitive data at rest (passwords, phone numbers, addresses, bank details) and in transit (HTTPS/TLS). Design key management and rotation procedures.

### 85. Password Security
**Prompt**: Implement strong password requirements (minimum length, complexity), hashing with bcrypt, password reset functionality with secure token generation, and password change enforcement.

### 86. Login Security & Account Lockout
**Prompt**: Design login security including failed attempt tracking, account lockout after N failures, account recovery procedures, and login history tracking with location and device information.

### 87. Vulnerability Scanning & Penetration Testing
**Prompt**: Design a security testing pipeline including static code analysis (SonarQube), dependency vulnerability scanning (Snyk), DAST (OWASP ZAP), and regular penetration testing. Create remediation tracking.

### 88. Data Backup & Recovery
**Prompt**: Implement automated daily database backups, test backup restoration, maintain multiple backup versions, and create disaster recovery procedures with RTO/RPO targets.

### 89. System Configuration Management
**Prompt**: Design an admin settings module for system-wide configuration: school name, contact info, academic calendar, holidays, fee settings, notification settings, and security parameters. Include change history.

### 90. Admin Activity Dashboard
**Prompt**: Create an admin activity dashboard showing system health, active users, system logs, recent critical operations, security alerts, and quick links to common admin tasks.

---

## Category 8: Reporting & Analytics (Prompts 91-100)

### 91. Custom Report Builder
**Prompt**: Design a self-service report builder allowing selection of report type, date ranges, filters (class, student, subject), metrics, and output format (PDF, Excel, CSV). Include saved report templates.

### 92. Dashboard Analytics
**Prompt**: Create role-specific analytics dashboards with KPI widgets, trend charts, performance metrics, and real-time data updates. Design interactive filtering and drill-down capability.

### 93. Scheduled Report Generation
**Prompt**: Implement scheduled report generation with cron-based scheduling, email distribution to configured recipients, and automatic export in specified formats.

### 94. Enrollment Analytics
**Prompt**: Design enrollment reports showing trend over years, class-wise distribution, gender breakdown, category analysis (SC/ST/OBC if applicable), and enrollment forecasting.

### 95. Academic Performance Report
**Prompt**: Create detailed academic performance reports showing subject-wise performance, class average trends, skill-wise performance, and student-specific growth tracking.

### 96. Financial Analytics Report
**Prompt**: Design financial reports showing revenue trends, fee collection efficiency, payment method breakdown, outstanding analysis, and forecasting for annual collection.

### 97. Staff Analytics Report
**Prompt**: Create reports on staff performance including classes taught, exam result quality, student feedback ratings, leave utilization, and attendance reliability.

### 98. Report Export & Email
**Prompt**: Implement multi-format export (PDF, Excel, CSV, JSON) with customizable formatting, email distribution capability, and scheduled delivery to stakeholders.

### 99. Data Visualization
**Prompt**: Design interactive visualizations using Chart.js/D3.js including line graphs (trends), bar charts (comparisons), pie charts (distributions), and heatmaps for pattern analysis.

### 100. Compliance & Audit Reports
**Prompt**: Design compliance reports for regulatory requirements including audit trails of data modifications, access logs, security incident reports, and data protection compliance documentation. Ensure non-repudiation and legal admissibility.

---

## Usage Guidelines

These prompts are designed for AI-assisted development where you can:

1. **Use with ChatGPT/Claude**: Feed individual prompts to generate code samples, architecture suggestions, or implementation approaches
2. **Modify prompts**: Adapt prompts to your specific tech stack (PHP/Laravel, Node.js, Java, etc.)
3. **Combine prompts**: Use multiple related prompts together for comprehensive module development
4. **Create variations**: Ask AI to create variations considering your specific requirements
5. **Code generation**: Ask for complete implementations, code snippets, or architectural patterns

Each prompt includes context, requirements, and scope to facilitate productive AI-assisted development.

