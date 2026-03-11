# School Management System - Development Prompts (AI-Assisted Development)

This document contains 100+ AI development prompts with enhanced details, implementation patterns, and code examples for building a complete School Management System using AI-assisted development.

## 📋 Quick Navigation

| Category | Prompts | Modules | Difficulty |
|----------|---------|---------|-----------|
| Student Management | 1-10 | Registration, Profile, Import, Search | Intermediate |
| Teacher Management | 11-20 | Onboarding, Schedule, Performance, Credentials | Intermediate |
| Attendance System | 21-30 | Daily Marking, Calculations, Reports, Leave | Advanced |
| Examination & Results | 31-50 | Scheduling, Marks, Grades, Analytics, Online Exams | Advanced |
| Fee Management | 51-70 | Structure, Payment, Invoices, Reconciliation | Advanced |
| Notifications & Communication | 71-80 | Email, SMS, Push, Templates, Announcements | Intermediate |
| Security & Admin | 81-90 | RBAC, 2FA, Audit Logs, Encryption, Backup | Advanced |
| Reporting & Analytics | 91-100 | Custom Reports, Dashboards, Exports, Compliance | Intermediate |

## 🎯 What's New in This Enhanced Version

### ✨ Enhanced Prompt Details Include:
- **Detailed Requirements**: Specific features and constraints for each module
- **Tech Stack Suggestions**: Recommendations for different frameworks and databases
- **Implementation Details**: Architecture, design patterns, and specific technical approaches
- **API Endpoints**: Complete REST API specifications for each feature
- **Performance Optimization**: Tips for handling large datasets and concurrent users
- **Security Considerations**: Security best practices and compliance requirements
- **Testing Guidelines**: Unit test, integration test, and API test recommendations
- **Code Examples**: Reference implementations and usage patterns

### 🚀 New Additions:
- **Design Patterns Section**: Common patterns used across prompts (Repository, Service Layer, Event-driven, etc.)
- **Technology-Specific Implementations**: Tips for Laravel, Node.js, React/Vue.js developers
- **Performance Optimization**: Database indexing, caching strategies, query optimization
- **Code Quality Checklist**: Ensure AI-generated code meets quality standards
- **Prompt Combinations**: Recommended prompts for end-to-end feature flows

## 📚 How to Use This Document

### For Beginners:
1. Choose a prompt from the category that interests you
2. Copy the entire prompt section
3. Paste into ChatGPT/Claude with your tech stack
4. Request code implementation
5. Use the provided API endpoints as reference

### For Experienced Developers:
1. Review the detailed requirements
2. Request specific implementations (e.g., "Implement in Laravel with Repository pattern")
3. Ask for performance optimizations
4. Request test cases and documentation
5. Use the implementation details as architectural blueprint

### For Teams:
1. Use prompt combinations for end-to-end modules
2. Assign prompts to team members
3. Use API endpoints for integration points
4. Reference design patterns for code consistency
5. Use testing guidelines for quality assurance

---

## Category 1: Student Management Module (Prompts 1-10)

### 1. Student Registration Feature (Advanced)
**Prompt**: You are a senior full-stack developer. Design and implement a comprehensive student registration module for a school management system. 

**Requirements**:
- Form validation: email uniqueness check, roll number format, date of birth validation (age >= 4, <= 25)
- Auto-generation of student ID using format: SCHOOL_CODE + YEAR + SEQUENTIAL_NUMBER (e.g., SMS202400001)
- Automatic user account creation with temporary password (12-char random, secure storage with bcrypt)
- Batch processing for multiple registration attempts
- Document upload handling (photo, birth certificate, admission form) with virus scanning
- GDPR compliance: consent collection, data minimization, retention policies
- Error handling: graceful validation failures, user-friendly error messages
- API response: standardized format with success/failure status, messages, and data

**Tech Stack Suggestions**:
- **Frontend**: React form with validation (Formik/React Hook Form), multi-step wizard
- **Backend**: Laravel/Node.js REST API with request validation middleware
- **Database**: MySQL transaction handling, unique constraint on email + roll number
- **Security**: HTTPS only, CSRF tokens, input sanitization, rate limiting on registration

**Implementation Details**:
- Implement Student model with fields: id, email, roll_number, dob, status, created_at
- Create StudentRepository for data access with transaction support
- Use queue system for sending welcome emails asynchronously
- Implement webhook for third-party system integration if needed
- Create unit tests for validation logic and API endpoints
- Add logging for registration attempts and failures

**Expected Output**: Working API endpoint, frontend form, documentation, and test cases.

### 2. Student Profile Management (Advanced)
**Prompt**: Create a comprehensive student profile management system with role-based data visibility and audit logging.

**Requirements**:
- **Profile Sections**: Personal info (name, DOB, gender, blood group), contact details (email, phone), emergency contacts (2-3 with relationships), documents (uploads with versioning), photo management, address information
- **Role-Based Visibility**: 
  - Student: sees own basic info + results
  - Parent: sees child's complete profile + academics
  - Teacher: sees only assigned class students, limited info
  - Admin: sees all information
- **Edit Functionality**: 
  - Each field has change tracking
  - Audit log of all modifications (who, when, what changed)
  - Soft updates with approval for critical fields
- **Features**: 
  - Bulk operations (export, update)
  - Search and filter
  - Document management with expiry tracking
  - Profile completion indicator

**Tech Stack Suggestions**:
- **Frontend**: React with permission-based component rendering
- **Backend**: Laravel/Node.js with middleware for role-based access control
- **Database**: MySQL with audit tables, versioning support
- **Caching**: Redis for frequently accessed profiles

**Implementation Details**:
- Create StudentProfile model with relationships to User, EmergencyContact, Document
- Implement Audit middleware to log all changes automatically
- Use Observers/Events for automated logging
- Create permission gates: canViewProfile($student), canEditProfile($student)
- Implement soft deletes for document archival
- Create query scopes for role-based filtering

**API Endpoints**:
- GET /api/v1/students/{id}/profile
- PUT /api/v1/students/{id}/profile
- GET /api/v1/students/{id}/documents
- POST /api/v1/students/{id}/documents
- GET /api/v1/students/{id}/audit-log

### 3. Bulk Student Import (Advanced)
**Prompt**: Design and implement a robust CSV import feature for bulk student registration with comprehensive error handling and data validation.

**Requirements**:
- **File Format**: CSV with headers (email, roll_number, first_name, last_name, dob, phone, etc.)
- **Validation**:
  - Duplicate detection (existing in DB + within same import)
  - Required field validation
  - Data type validation (email format, date format, numeric roll numbers)
  - Uniqueness constraints (email, roll number)
  - Age validation (4-25 years)
- **Error Handling**:
  - Detailed error report per row (row number, field, error message)
  - Option to retry with corrected data
  - Transaction rollback on critical errors
- **Features**:
  - Preview before import
  - Success/failure summary
  - Auto-generation of student IDs for successful records
  - Mapping of CSV columns to system fields
  - Skip existing records option

**Tech Stack Suggestions**:
- **Frontend**: React with file upload, progress tracking, error display
- **Backend**: Laravel/Node.js with queue processing for large files
- **Storage**: Temporary storage for CSV files, cleanup after processing
- **Database**: Transactions for atomic operations

**Implementation Details**:
- Create StudentImport model to track import jobs
- Use Laravel Jobs/Node.js Bull for async processing
- Implement batch processing: import in chunks of 100-500 records
- Create validation rules using custom validators
- Generate detailed import logs
- Implement retry mechanism with exponential backoff
- Create progress tracking via WebSockets/Polling

**API Endpoints**:
- POST /api/v1/students/import/upload (file upload)
- GET /api/v1/students/import/{jobId}/preview (preview data)
- POST /api/v1/students/import/{jobId}/execute (start import)
- GET /api/v1/students/import/{jobId}/status (check status)
- GET /api/v1/students/import/{jobId}/report (error report)

### 4. Student Search & Filter (Advanced)
**Prompt**: Implement an advanced search and filter system for student management with elasticsearch integration and real-time autocomplete.

**Requirements**:
- **Search Features**:
  - Full-text search: name, email, roll number, phone
  - Partial matching with fuzzy search
  - Autocomplete suggestions
  - Search history for quick access
- **Filtering**:
  - Single select: class, section, status, enrollment year
  - Multi-select: multiple classes, categories
  - Range filters: DOB, enrollment date
  - Boolean filters: has documents, fee paid, etc.
- **Advanced Options**:
  - Saved search filters
  - Export search results
  - Bulk actions on filtered results
- **Performance**:
  - Pagination with customizable page size (10, 25, 50, 100)
  - Lazy loading for large result sets
  - Caching of popular searches

**Tech Stack Suggestions**:
- **Frontend**: React with form state management, real-time suggestions
- **Backend**: Laravel/Node.js with Elasticsearch integration
- **Search**: Elasticsearch 7+ for full-text search capabilities
- **Caching**: Redis for search suggestions and popular filters

**Implementation Details**:
- Create Student index in Elasticsearch with analyzed fields
- Implement SearchRepository with query builders
- Use Laravel Scouts or Node.js client for ES integration
- Create cache layer for autocomplete suggestions
- Implement search analytics (popular searches, zero-result searches)
- Create filters using filterable traits/mixins

**API Endpoints**:
- GET /api/v1/students/search?q=john (search)
- GET /api/v1/students/autocomplete?q=jo (autocomplete)
- POST /api/v1/students/filter (advanced filter)
- POST /api/v1/students/saved-filters (save filter)
- GET /api/v1/students/saved-filters (list saved filters)

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

### 21. Daily Attendance Marking (Advanced)
**Prompt**: Create an intelligent and intuitive attendance marking system with offline support, real-time notifications, and comprehensive analytics.

**Requirements**:
- **Quick Actions**:
  - Mark all present (single click)
  - Mark by section/group
  - Undo last action
  - Bulk operations (select multiple students)
- **Attendance Types**: Present, Absent, Leave, Late (with configurable late time threshold)
- **Features**:
  - Attendance remarks (optional notes)
  - Automatic parent notifications for absences via SMS/email
  - Leave request approval integration
  - Offline sync capability (save locally, sync when online)
- **Validation**:
  - Prevent duplicate marking (same day)
  - Prevent future date marking
  - Require remarks for unusual patterns
- **Performance**:
  - Lightning-fast UI for 100+ students
  - Minimal database queries
  - Real-time update to dashboards

**Tech Stack Suggestions**:
- **Frontend**: React with offline support (Service Workers), optimistic updates
- **Backend**: Node.js/Laravel with bulk insert operations
- **Database**: MySQL with indexed queries on (class_id, date, student_id)
- **Offline**: LocalStorage/IndexedDB for offline data storage
- **Real-time**: WebSockets for live updates

**Implementation Details**:
- Create AttendanceRecord model with unique constraint (student_id, date)
- Implement bulk insert for performance: INSERT IGNORE or ON DUPLICATE KEY
- Create attendance cache: Redis key = "attendance:class:{id}:date"
- Use database transactions for atomic operations
- Implement queue for notification sending
- Create Service Worker for offline support
- Implement data sync strategy: queue-based or differential sync

**Complex Logic**:
```
Attendance Percentage Calculation:
- Total Working Days = Calendar days - Sundays - Holidays
- Present Count = Days with 'Present' status
- Percentage = (Present Count / Total Working Days) * 100
- Late to Absent: if late_count > threshold, mark as absent for eligibility
```

**API Endpoints**:
- POST /api/v1/attendance/mark (single marking)
- POST /api/v1/attendance/mark-bulk (bulk marking)
- GET /api/v1/attendance/class/{id}/date/{date} (get day attendance)
- PUT /api/v1/attendance/{id} (update/undo)
- GET /api/v1/attendance/stats (daily statistics)
- GET /api/v1/attendance/sync (offline sync)

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

### 33. Marks Entry Interface (Advanced)
**Prompt**: Design a high-performance marks entry system for teachers with formula-based calculations, validation, and batch processing capabilities.

**Requirements**:
- **Input Methods**:
  - Individual marks entry
  - Spreadsheet-style bulk entry (editable table)
  - Copy marks from previous exam
  - Import from Excel template
- **Validation**:
  - Marks within configured range (e.g., 0-100)
  - Prevent negative marks (unless configured)
  - Percentage validation (auto-calculate from marks)
  - Grade auto-assignment based on percentage
  - Flagging marks outside normal distribution (outliers)
- **Calculations**:
  - Formula-based: percentage = (marks/total) * 100
  - Grade mapping: 90-100 = A, 80-90 = B, etc.
  - Subject total from multiple assessments
  - Class average calculation
  - Custom formulas support
- **Features**:
  - Auto-save (every keystroke or interval-based)
  - Undo/redo functionality
  - Batch submission with approval workflow
  - Marks lock after publication to prevent accidental changes
  - Comments/feedback per student
  - Historical comparison (this exam vs previous)

**Tech Stack Suggestions**:
- **Frontend**: React with grid library (ag-Grid, react-table), formula support
- **Backend**: Node.js/Laravel with caching for calculations
- **Database**: MySQL with triggers for automatic calculations
- **Optimization**: Denormalization for frequently accessed calculated values

**Implementation Details**:
- Create MarksEntry model with fields: exam_id, student_id, subject_id, marks, percentage, grade
- Implement transaction-based batch insertion for consistency
- Use database triggers for auto-calculation: `AFTER INSERT ON marks_entry FOR EACH ROW SET percentage = (marks/total)*100`
- Create cache invalidation strategy when marks change
- Implement formula evaluation engine using math expression parser
- Create audit trail for all changes
- Implement optimistic locking to prevent concurrent edits

**Performance Optimization**:
- Lazy load student data (500 at a time)
- Virtual scrolling for large datasets
- Batch API calls (save 10-20 marks in single request)
- Debounce auto-save (save after 2 seconds of inactivity)

**API Endpoints**:
- POST /api/v1/exams/{examId}/marks/entry (single entry)
- POST /api/v1/exams/{examId}/marks/bulk (bulk entry)
- GET /api/v1/exams/{examId}/marks (get all marks)
- PUT /api/v1/marks/{id} (update)
- POST /api/v1/exams/{examId}/marks/submit (batch submit)
- POST /api/v1/exams/{examId}/marks/undo (undo operation)

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

### 53. Payment Processing (Advanced)
**Prompt**: Implement a secure and flexible payment processing system supporting multiple payment gateways with automatic reconciliation and compliance.

**Requirements**:
- **Payment Methods**:
  - Cash payment (with receipt generation)
  - Check payment (with check details, maturity date, bank info)
  - Online payment (Credit/Debit card, Net Banking)
  - Bank transfer (with reference number tracking)
  - Wallet/Prepaid balance
- **Payment Recording**:
  - Immediate payment confirmation
  - Receipt generation (printable, downloadable, email)
  - Transaction ID storage for reconciliation
  - Payment date, amount, method, remarks
  - Partial payment support (for installments)
- **Integration**:
  - Stripe/PayPal integration for online payments
  - PCI DSS compliance (use payment gateway, never store card data)
  - Webhook handling for payment status updates
  - Automatic reconciliation with bank statements
- **Features**:
  - Payment history tracking
  - Multiple transaction attempt logging
  - Refund tracking (partial/full)
  - Payment reversal (for cash/check)
  - Failed payment retry logic
  - Invoice generation for tax compliance

**Tech Stack Suggestions**:
- **Frontend**: React with secure payment form (Stripe Elements)
- **Backend**: Node.js/Laravel with payment gateway SDKs
- **Payment**: Stripe/PayPal for PCI compliance
- **Database**: MySQL with transactions for atomic operations
- **Queue**: Redis/Bull for async reconciliation

**Implementation Details**:
- Create Payment model with fields: student_id, amount, method, status, transaction_id, gateway_response
- Create PaymentGateway interface with Stripe, PayPal implementations
- Use Strategy pattern for different payment methods
- Implement webhook handler for payment status updates
- Create transaction-based payment recording (atomic operations)
- Implement idempotency key to prevent duplicate charges
- Create daily reconciliation job: compare DB payments with gateway records
- Implement payment state machine: pending → processing → success/failed

**Security Considerations**:
- Never store card data (use Stripe tokenization)
- Use HTTPS/TLS for all payment communications
- Implement rate limiting on payment endpoints
- Validate webhook signatures from payment gateway
- Encrypt sensitive payment data at rest
- Log all payment attempts (not full card details)

**API Endpoints**:
- POST /api/v1/payments (record payment)
- POST /api/v1/payments/online (initiate online payment)
- GET /api/v1/payments/online/{paymentId}/status (check status)
- POST /api/v1/payments/webhook (payment gateway webhook)
- POST /api/v1/payments/{id}/refund (process refund)
- GET /api/v1/payments/receipt/{id} (generate receipt)
- GET /api/v1/payments/reconciliation/status (check reconciliation)

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

---

## Advanced: Implementation Patterns & Code Examples

### Common Patterns Used in These Prompts

#### 1. Repository Pattern
```
Purpose: Abstract data access layer
Usage: Used in Student Management, Attendance, Payment modules
Benefits: Testability, reusability, easy database switching
```

#### 2. Service Layer Pattern
```
Purpose: Business logic separation
Usage: Fee calculation, attendance percentage, result generation
Benefits: Reusable logic, transaction handling, complex operations
```

#### 3. Event/Observer Pattern
```
Purpose: Reactive programming
Usage: Student registration → send welcome email, mark changes → audit log
Benefits: Loose coupling, scalability, extensibility
```

#### 4. Strategy Pattern
```
Purpose: Multiple algorithms for same operation
Usage: Payment processing (cash, card, bank transfer), fee calculation (percentage, fixed)
Benefits: Flexibility, runtime selection, easy addition of new strategies
```

#### 5. State Machine Pattern
```
Purpose: Manage state transitions
Usage: Payment (pending→processing→success), Result (draft→submitted→approved→published)
Benefits: Clear state logic, prevents invalid transitions, audit trail
```

### Technology-Specific Implementations

#### For Laravel Developers
```
- Use Models + Eloquent ORM
- Implement scopes for reusable queries
- Use Service classes for business logic
- Leverage Jobs for queuing
- Use Events/Listeners for reactive updates
- Implement Policies for authorization
- Use Transactions for data consistency
```

#### For Node.js/Express Developers
```
- Use async/await for clean async code
- Implement middleware for cross-cutting concerns
- Use class-based services for organization
- Leverage Bull/Bee-queue for job processing
- Use EventEmitter for event-driven architecture
- Implement middleware for validation/authentication
- Use transactions with connection pooling
```

#### For React/Vue.js Frontend
```
- Use hooks for stateful logic (useState, useEffect, useContext)
- Implement API client abstraction layer
- Use state management (Redux/Vuex) for complex state
- Implement error boundaries for error handling
- Use memoization for performance optimization
- Implement offline support with service workers
- Use form libraries for complex forms (Formik, React Hook Form)
```

### Common Validations Across Modules

#### Date Validations
```
- DOB: Must be 4-25 years old (for students)
- Exam date: Cannot be in past
- Fee due date: Must be after fee assignment
- Leave date: Cannot overlap with existing leave
```

#### Status Validations
```
- Student status transition: Active → (Inactive/Withdrawn/Transferred)
- Payment status: Pending → (Processing → Success) OR Failed
- Result publication: Draft → Submitted → Approved → Published
```

#### Uniqueness Constraints
```
- Email: Unique per student
- Roll number: Unique per class per academic year
- Exam code: Unique per academic year
- Account number: Unique in system
```

### Performance Optimization Tips

1. **Database Indexing**:
   - Index on frequently searched fields (student_id, class_id, date)
   - Composite indexes for multi-column filters
   - Regular index analysis and optimization

2. **Caching Strategy**:
   - Cache student profiles (30 min TTL)
   - Cache attendance percentage (24 hour TTL)
   - Cache fee structure (7 day TTL)
   - Use cache tags for invalidation

3. **Query Optimization**:
   - Use eager loading (prevent N+1 queries)
   - Implement pagination for large datasets
   - Use database views for complex aggregations
   - Denormalize for frequently accessed calculated fields

4. **Async Processing**:
   - Use queues for email sending, report generation
   - Process bulk operations asynchronously
   - Generate PDF reports in background
   - Sync with payment gateways async

### Testing Considerations

Each prompt should include:
- **Unit Tests**: Test individual functions (validation, calculation)
- **Integration Tests**: Test API endpoints with database
- **API Tests**: Test all endpoints with various inputs
- **UI Tests**: Test user interactions (Cypress, Playwright)
- **Security Tests**: Test authentication, authorization, input validation

### Documentation Requirements

For each implemented feature:
- API endpoint documentation
- Database schema documentation
- Business logic documentation
- Configuration documentation
- Setup and deployment guide

---

## Usage Guidelines for AI-Assisted Development

### How to Use These Enhanced Prompts

1. **Direct Use with ChatGPT/Claude**:
   - Copy entire prompt section
   - Request code implementation
   - Ask for architectural explanation
   - Request test case generation
   - Ask for SQL schema

2. **Adapt to Your Tech Stack**:
   - If using Laravel: request Laravel-specific implementation
   - If using Node.js: request Express/Nest.js implementation
   - If using Python: request Django/FastAPI implementation
   - Specify database (MySQL, PostgreSQL, etc.)

3. **Request Code Examples**:
   - Ask for complete API endpoint implementation
   - Request model/schema definition
   - Ask for validation rules
   - Request test cases

4. **Combine Related Prompts**:
   - Student Registration (Prompt 1) + Bulk Import (Prompt 3) for complete enrollment module
   - Attendance Marking (Prompt 21) + Attendance Reports (Prompt 23) for complete attendance system
   - Marks Entry (Prompt 33) + Result Publication (Prompt 35) for examination module

5. **Create Variations**:
   - "Create this for universities instead of schools"
   - "Add mobile-first considerations"
   - "Add offline-first architecture"
   - "Make this HIPAA-compliant for healthcare data"

### Recommended Prompt Combinations

**Student Enrollment Flow**:
1. Student Registration (1)
2. Bulk Import (3)
3. Document Management (8)
4. Communication Preferences (9)

**Examination & Results**:
1. Exam Scheduling (31)
2. Marks Entry (33)
3. Result Publication (35)
4. Result Slip Generation (36)
5. Performance Analytics (38)

**Fee Management**:
1. Fee Structure (51)
2. Fee Assignment (52)
3. Payment Processing (53)
4. Fee Reports (59)
5. Accounting Integration (64)

**Communication & Notifications**:
1. In-App Notifications (71)
2. Email Service (72)
3. SMS Service (73)
4. Announcement Management (78)
5. Preference Management (79)

### Best Practices for AI-Assisted Development

1. **Be Specific**: Include technology stack, version, and specific requirements
2. **Request Incrementally**: Ask for one feature at a time, then integrate
3. **Verify Output**: Always verify AI-generated code for security and correctness
4. **Test Thoroughly**: Write comprehensive tests for AI-generated code
5. **Document Well**: Ensure all implementations are documented
6. **Security First**: Always ask for security considerations
7. **Performance Focus**: Request performance optimization suggestions
8. **Error Handling**: Ensure proper error handling is implemented

### Quality Checklist for AI-Generated Code

- [ ] Follows project coding standards
- [ ] Includes error handling
- [ ] Includes input validation
- [ ] Includes unit tests
- [ ] Includes documentation
- [ ] Follows security best practices
- [ ] Includes proper logging
- [ ] Performance optimized
- [ ] Includes API examples
- [ ] Database schema included

Each prompt includes context, requirements, scope, technology suggestions, implementation details, and API endpoint specifications to facilitate productive AI-assisted development.

