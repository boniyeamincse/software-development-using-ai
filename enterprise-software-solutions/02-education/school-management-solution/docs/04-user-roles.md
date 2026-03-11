# School Management System - User Roles & Permissions

## 1. Role Overview

The School Management System implements a Role-Based Access Control (RBAC) system with 6 primary roles, each with specific permissions and responsibilities.

---

## 2. Role Definitions

### 2.1 Super Admin

**Description**: Highest level user with complete system access and control.

**Responsibilities**:
- User management (create, edit, delete, reset passwords)
- Role and permission management
- System configuration and settings
- Backup and recovery operations
- Audit log review
- System monitoring and performance tuning
- Database maintenance
- Security policy enforcement

**Login Access**: Email/Username + Password + 2FA (recommended)

---

### 2.2 Admin

**Description**: Administrative user managing school operations and user access.

**Responsibilities**:
- Create and manage student accounts
- Create and manage teacher accounts
- Manage classes and sections
- Oversee holiday and academic calendar
- Generate reports (all types)
- Manage system configurations
- Approve fee waivers and discounts
- Monitor system activities
- User access and authentication support

**Login Access**: Email/Username + Password

---

### 2.3 Teacher

**Description**: Academic staff managing classrooms and student assessments.

**Responsibilities**:
- Mark student attendance
- Create and manage assignments
- Upload exam marks and grades
- Generate result slips
- Submit reports
- Communicate with students and parents
- Update subject content and curriculum
- Track student progress
- View class-wise reports

**Login Access**: Email/Username + Password

---

### 2.4 Student

**Description**: Educational institution users accessing academic information.

**Responsibilities**:
- View personal academic information
- Check attendance records
- View exam schedule and results
- Download result slips and transcripts
- Check fee status
- Receive notifications and announcements
- Communicate with teachers
- View class schedule

**Login Access**: Email/Username + Password

---

### 2.5 Parent

**Description**: Guardians monitoring student progress and institutional communication.

**Responsibilities**:
- View child's academic progress
- Monitor child's attendance
- Check fee payment status
- Download invoices
- Communicate with teachers
- Receive notifications about child's activities
- Manage personal account settings
- View school announcements and calendar

**Login Access**: Email/Username + Password

---

### 2.6 Accountant

**Description**: Financial staff managing fees and payments.

**Responsibilities**:
- Record fee payments
- Generate invoices
- Process refunds
- Generate financial reports
- Manage payment methods
- Track fee collection
- Manage discounts and concessions
- Audit fee transactions
- Generate financial statements

**Login Access**: Email/Username + Password

---

## 3. Permission Matrix

| Module/Feature | Super Admin | Admin | Teacher | Student | Parent | Accountant |
|---|:---:|:---:|:---:|:---:|:---:|:---:|
| **User Management** | | | | | | |
| Create User | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| Edit User | ✅ | ✅ | ❌ | ⚠️* | ❌ | ❌ |
| Delete User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Reset Password | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| Assign Roles | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Manage Permissions | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| **Student Management** | | | | | | |
| Create Student | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| Edit Student | ✅ | ✅ | ⚠️† | ⚠️* | ❌ | ❌ |
| Delete Student | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| View Student Profile | ✅ | ✅ | ✅ | ⚠️* | ⚠️† | ✅ |
| Student Search | ✅ | ✅ | ✅ | ❌ | ⚠️† | ✅ |
| **Teacher Management** | | | | | | |
| Create Teacher | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| Edit Teacher | ✅ | ✅ | ⚠️* | ❌ | ❌ | ❌ |
| Delete Teacher | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| View Teacher Profile | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| **Class Management** | | | | | | |
| Create Class | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| Edit Class | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| Delete Class | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| Assign Students | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| Assign Teachers | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| View Class Info | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| **Attendance** | | | | | | |
| Mark Attendance | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ |
| Approve Attendance | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| View Attendance | ✅ | ✅ | ✅ | ⚠️* | ⚠️† | ❌ |
| Edit Attendance | ✅ | ✅ | ⚠️§ | ❌ | ❌ | ❌ |
| Attendance Reports | ✅ | ✅ | ✅ | ❌ | ⚠️† | ❌ |
| **Examination** | | | | | | |
| Create Exam | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| Edit Exam | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| Delete Exam | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| Generate Admit Card | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| View Exam Schedule | ✅ | ✅ | ✅ | ⚠️* | ⚠️† | ❌ |
| **Result Management** | | | | | | |
| Enter Marks | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ |
| Approve Results | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| Publish Results | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| View Results | ✅ | ✅ | ✅ | ⚠️* | ⚠️† | ❌ |
| Generate Transcripts | ✅ | ✅ | ⚠️§ | ❌ | ❌ | ❌ |
| **Fee Management** | | | | | | |
| Create Fee Structure | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| Edit Fee Structure | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| Record Payment | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ |
| Generate Invoice | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ |
| View Fee Status | ✅ | ✅ | ❌ | ⚠️* | ⚠️† | ✅ |
| Process Refund | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ |
| Approve Discount | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| **Reporting** | | | | | | |
| View All Reports | ✅ | ✅ | ⚠️† | ❌ | ❌ | ⚠️† |
| Generate Custom Reports | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ |
| Export Reports | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ |
| Schedule Reports | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| **System Administration** | | | | | | |
| Configure Settings | ✅ | ⚠️‡ | ❌ | ❌ | ❌ | ❌ |
| Manage Backup | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| View Audit Logs | ✅ | ⚠️‡ | ❌ | ❌ | ❌ | ❌ |
| User Activity Monitoring | ✅ | ⚠️‡ | ❌ | ❌ | ❌ | ❌ |
| Manage Holidays | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| **Notifications** | | | | | | |
| Send Announcements | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ |
| Manage Templates | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |
| View Notifications | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| **Document Management** | | | | | | |
| Upload Documents | ✅ | ✅ | ✅ | ⚠️* | ⚠️* | ❌ |
| Download Documents | ✅ | ✅ | ✅ | ⚠️* | ⚠️* | ❌ |
| Delete Documents | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |

**Legend:**
- ✅ = Full access
- ❌ = No access
- ⚠️ = Conditional access
- `*` = Only own data
- `†` = Only child's/related student data
- `§` = Class-wise only
- `‡` = Limited access (read-only)

---

## 4. Permission Definitions

### Student-Related Permissions

| Permission | Code | Description |
|---|---|---|
| View Own Profile | `student:view_own_profile` | View personal information |
| Edit Own Profile | `student:edit_own_profile` | Update personal details |
| View Own Attendance | `student:view_own_attendance` | View personal attendance records |
| View Own Results | `student:view_own_results` | View personal academic results |
| View Own Fee Status | `student:view_own_fee_status` | Check fee payment status |
| Download Transcript | `student:download_transcript` | Generate academic transcript |
| View Exam Schedule | `student:view_exam_schedule` | View examination schedule |

### Teacher-Related Permissions

| Permission | Code | Description |
|---|---|---|
| Mark Attendance | `teacher:mark_attendance` | Record student attendance |
| Enter Marks | `teacher:enter_marks` | Submit exam marks |
| View Class | `teacher:view_class` | View assigned class details |
| Generate Reports | `teacher:generate_reports` | Create academic reports |
| Communicate Students | `teacher:communicate_students` | Message students and parents |
| Update Curriculum | `teacher:update_curriculum` | Modify course content |

### Admin-Related Permissions

| Permission | Code | Description |
|---|---|---|
| Manage Users | `admin:manage_users` | Create and edit user accounts |
| Manage Students | `admin:manage_students` | Handle student operations |
| Manage Teachers | `admin:manage_teachers` | Handle teacher operations |
| Manage Classes | `admin:manage_classes` | Create and configure classes |
| View All Reports | `admin:view_all_reports` | Access all system reports |
| Configure System | `admin:configure_system` | Modify system settings |
| View Audit Logs | `admin:view_audit_logs` | Access system activity logs |

### Accountant-Related Permissions

| Permission | Code | Description |
|---|---|---|
| Record Payment | `accountant:record_payment` | Document fee payments |
| Generate Invoice | `accountant:generate_invoice` | Create fee invoices |
| View Financial Data | `accountant:view_financial_data` | Access financial information |
| Generate Reports | `accountant:generate_reports` | Create financial reports |
| Process Refund | `accountant:process_refund` | Handle fee refunds |

### Super Admin-Related Permissions

| Permission | Code | Description |
|---|---|---|
| Manage All Users | `superadmin:manage_all_users` | Full user account control |
| Manage Roles | `superadmin:manage_roles` | Create and edit roles |
| Manage Permissions | `superadmin:manage_permissions` | Define system permissions |
| System Backup | `superadmin:system_backup` | Create database backups |
| System Security | `superadmin:system_security` | Manage security settings |
| Audit Control | `superadmin:audit_control` | Full audit log access |

---

## 5. Access Control Rules

### 5.1 Data Isolation
- Students can only view their own data
- Parents can only view their children's data
- Teachers can only view their assigned class data
- Accountants can only view fee-related data
- Admins can view all institutional data
- Super Admin has unrestricted access

### 5.2 Cross-Role Access
- Students cannot modify any data
- Parents cannot access any administration features
- Teachers cannot access financial operations
- Accountants cannot access academic operations
- Admins cannot access super admin features

### 5.3 Time-Based Access Control
- Exam results visible only after publication
- Fee payments visible only to fee payers
- Attendance visible with configured delay
- Sensitive data access logged and audited

### 5.4 Data Sensitivity Levels

**Level 1 - Public** (accessible to authenticated users)
- General announcements
- Holiday calendar
- General academic calendar

**Level 2 - Confidential** (role-restricted)
- Student personal information
- Teacher credentials
- Examination details

**Level 3 - Restricted** (admin only)
- Financial transactions
- User access logs
- System configurations

**Level 4 - Highly Restricted** (super admin only)
- Backup operations
- Permission management
- System security settings

---

## 6. Role-Based Dashboards

### Super Admin Dashboard
- System health overview
- User activity summary
- System performance metrics
- Recent audit logs
- Backup status

### Admin Dashboard
- Student enrollment overview
- Fee collection status
- Teacher performance metrics
- Attendance analytics
- System notifications
- Quick access to all management modules

### Teacher Dashboard
- Class list and schedule
- Attendance overview
- Assignment list
- Result submission status
- Messages from students/parents
- Class performance analytics

### Student Dashboard
- Personal academic info
- Current class and schedule
- Attendance percentage
- Exam schedule
- Recent results
- Fee status
- School announcements

### Parent Dashboard
- Child's academic progress
- Attendance tracking
- Exam schedule and results
- Fee payment status
- School announcements
- Messages from teachers

### Accountant Dashboard
- Fee collection summary
- Pending payments
- Daily transaction summary
- Report generation quick links
- Payment method breakdown

---

## 7. Implementation Guidelines

### Authentication
1. All role-based access is enforced at the API level
2. JWT tokens include role and permission claims
3. API endpoints validate user permissions before processing requests
4. Multiple role assignments are supported

### Logging & Auditing
1. All permission-based access is logged
2. Permission denial attempts are recorded
3. Sensitive operations require additional approval
4. Audit logs are immutable and time-stamped

### Security Best Practices
1. Principle of Least Privilege: Users get minimum required permissions
2. Regular permission audits and reviews
3. Role separation to prevent conflicts of interest
4. Multi-factor authentication for sensitive roles

---

## Summary

The School Management System implements a comprehensive RBAC model with 6 primary roles, each with specific permissions and responsibilities. The permission matrix ensures secure data access while enabling efficient operations across different user types. All access is logged and audited for compliance and security purposes.

