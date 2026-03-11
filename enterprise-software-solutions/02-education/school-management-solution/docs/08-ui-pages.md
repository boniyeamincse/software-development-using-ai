# School Management System - UI Pages

## 1. Public Pages (No Authentication Required)

### 1.1 Login Page
**URL:** `/login`

**Features:**
- Email/Username field
- Password field
- "Remember Me" checkbox
- "Forgot Password" link
- Language selector
- Responsive design
- CSRF protection

**Elements:**
- School logo
- Login form
- Error messages display
- Loading indicator
- Social login options (optional)

---

### 1.2 Register Page
**URL:** `/register`

**Features:**
- User type selection (Student, Parent, Teacher)
- First name & Last name
- Email & Phone
- Password & Confirm password
- Terms acceptance checkbox
- Captcha verification
- Form validation with inline errors

---

### 1.3 Forgot Password Page
**URL:** `/forgot-password`

**Features:**
- Email input field
- OTP verification
- New password form
- Success confirmation
- Resend OTP option

---

## 2. Authentication Pages

### 2.1 Dashboard (Role-Specific)

#### Student Dashboard
**URL:** `/dashboard`

**Widgets:**
- Profile card
- Current class info
- Attendance percentage (this month)
- Next exam schedule (coming 7 days)
- Latest results
- Fee payment status
- Pending assignments
- School announcements

**Quick Actions:**
- Download admit card
- View full attendance
- Download transcript
- Pay fees online

---

#### Teacher Dashboard
**URL:** `/teacher/dashboard`

**Widgets:**
- Profile info
- My classes (this term)
- Today's schedule
- Classes with pending attendance
- Recent mark entries
- Assignment submission status
- Class performance overview
- Notifications

**Quick Actions:**
- Mark attendance
- Enter marks
- Send message
- View reports

---

#### Parent Dashboard
**URL:** `/parent/dashboard`

**Widgets:**
- Child selection (for multiple children)
- Child's academic progress
- Attendance overview
- Exam schedule
- Latest results
- Fee payment status
- School announcements
- Teacher messages

**Quick Actions:**
- View detailed attendance
- View fee invoices
- Pay fees online
- Message teacher

---

#### Admin Dashboard
**URL:** `/admin/dashboard`

**Widgets:**
- Key metrics (students, teachers, classes, etc.)
- Fee collection status
- Attendance overview
- Recent registrations
- System health
- User activity log
- Notifications
- Quick statistics

**Quick Actions:**
- Create student
- Create teacher
- Create class
- Generate report
- System settings

---

#### Accountant Dashboard
**URL:** `/accountant/dashboard`

**Widgets:**
- Today's collection
- Monthly revenue
- Outstanding amounts
- Payment methods breakdown
- Recent transactions
- Pending payments
- Financial summary

**Quick Actions:**
- Record payment
- Generate invoice
- View fee reports
- Process refund

---

## 3. Student Management Pages

### 3.1 Student List
**URL:** `/admin/students`

**Features:**
- Table with pagination
- Search bar (by name, roll number, email)
- Filter by class, status
- Sort by any column
- Action buttons (view, edit, delete)
- Bulk operations
- Export to Excel/PDF
- Add new student button

**Columns:**
- Roll Number
- Name
- Class
- Email
- Status
- Created Date
- Actions

---

### 3.2 Student Profile
**URL:** `/students/{id}` (student view)
**URL:** `/admin/students/{id}` (admin view)

**Sections:**
- Personal information
- Contact details
- Academic information
- Emergency contacts
- Document uploads
- Attendance history
- Results history
- Fee payment history

**Edit Permission:**
- Students: Can edit own profile (limited fields)
- Admin: Can edit all fields

---

### 3.3 Add/Edit Student
**URL:** `/admin/students/create`
**URL:** `/admin/students/{id}/edit`

**Form Fields:**
- First name, Last name
- Email, Phone
- Date of birth, Gender
- Address, City, State, Postal Code
- Class selection
- Roll number
- Section
- Emergency contact name & phone
- Profile photo upload
- Status (Active, Inactive)

**Validation:**
- Email unique check
- Roll number unique within class
- DOB not in future
- Phone format validation

---

### 3.4 Student Search & Filter
**URL:** `/admin/students`

**Search Options:**
- By name
- By roll number
- By email
- By class
- By status

**Filters:**
- Class (dropdown)
- Section (dropdown)
- Status (dropdown)
- Date range (enrollment)
- Academic year

---

## 4. Teacher Management Pages

### 4.1 Teacher List
**URL:** `/admin/teachers`

**Features:**
- Teacher table with pagination
- Search by name, employee ID, email
- Filter by subject, class, status
- Action buttons
- Bulk operations
- Add new teacher button

---

### 4.2 Teacher Profile
**URL:** `/teachers/{id}`

**Sections:**
- Personal information
- Employment details
- Qualifications & Certifications
- Subject assignments
- Class assignments
- Schedule
- Performance metrics
- Activity log

---

### 4.3 Add/Edit Teacher
**URL:** `/admin/teachers/create`
**URL:** `/admin/teachers/{id}/edit`

**Form Fields:**
- First name, Last name
- Email, Phone
- Employee ID
- Date of birth, Gender
- Address
- Qualifications
- Specialization
- Hire date
- Status
- Profile photo
- Bank details (if applicable)

---

## 5. Class Management Pages

### 5.1 Class List
**URL:** `/admin/classes`

**Features:**
- Classes table
- Filter by academic year
- Search by name
- View class details
- Edit class
- Manage students
- View timetable
- Add new class

---

### 5.2 Class Details
**URL:** `/admin/classes/{id}`

**Sections:**
- Class information
- Student list (with strength)
- Class teacher info
- Subject list
- Timetable
- Teacher assignments
- Performance metrics

**Actions:**
- Edit class
- Assign students
- Assign teacher
- View/Print timetable

---

### 5.3 Manage Class Students
**URL:** `/admin/classes/{id}/students`

**Features:**
- Current student list
- Add students button
- Remove student button
- Search students
- Bulk assign
- Import from file

---

## 6. Attendance Pages

### 6.1 Mark Attendance
**URL:** `/teacher/attendance/mark`

**Features:**
- Class selection dropdown
- Date picker
- Student list with checkboxes
- Mark present/absent/leave
- Bulk operations (Mark all present)
- Save button
- Previous attendance view (optional)

**Workflow:**
1. Select class
2. Select date
3. Mark attendance
4. Add remarks (optional)
5. Submit

---

### 6.2 Attendance Records
**URL:** `/student/attendance` (student view)
**URL:** `/teacher/attendance` (teacher view)
**URL:** `/admin/attendance` (admin view)

**Features:**
- Calendar view or list view
- Filter by month
- Attendance percentage display
- Leave records
- Export to PDF

---

### 6.3 Attendance Report
**URL:** `/reports/attendance`

**Features:**
- Date range picker
- Class/student selector
- Attendance percentage chart
- Attendance breakdown (Present/Absent/Leave)
- Export options
- Print report

---

## 7. Examination Pages

### 7.1 Exam Schedule
**URL:** `/exams/schedule`

**Features:**
- Calendar view
- List view
- Filter by class, subject
- Color-coded exam types
- Admit card download
- Exam details
- Date/time confirmation

---

### 7.2 Create/Edit Exam
**URL:** `/admin/exams/create`
**URL:** `/admin/exams/{id}/edit`

**Form Fields:**
- Exam name
- Class selection
- Subject selection
- Exam date & time
- Duration
- Total marks
- Passing marks
- Exam type (dropdown)
- Room assignment

---

### 7.3 Admit Card
**URL:** `/exams/{id}/admit-card`

**Display:**
- Student photo
- Name, Roll number
- Class, Section
- Exam details
- Exam center
- Date/Time
- Instructions
- Signature line
- Print button

---

## 8. Result Pages

### 8.1 Enter Marks/Results
**URL:** `/teacher/results/enter`

**Features:**
- Exam selection
- Student list with marks entry
- Auto-calculate percentage & grade
- Validation (marks within range)
- Submit button
- Save as draft option
- Previous entries view

---

### 8.2 View Results
**URL:** `/student/results` (student view)
**URL:** `/results` (admin/teacher view)

**Features:**
- Filter by exam, class
- Search by student
- Sort options
- Result slip download
- Performance graph
- Subject-wise comparison

---

### 8.3 Result Slip/Report Card
**URL:** `/results/{id}/slip`

**Display:**
- Header (school name, logo)
- Student information
- Class & section
- Exam name & date
- Subject-wise marks & grades
- Total, percentage, overall grade
- Class rank/position
- Teacher signature line
- Principal signature line
- Print button

---

## 9. Fee Management Pages

### 9.1 Fee Structure
**URL:** `/admin/fees/structure`

**Features:**
- List of fee structures
- Create new structure
- Edit structure
- Delete structure
- Assign students
- View assigned students

---

### 9.2 Student Fee Status
**URL:** `/student/fees` (student view)
**URL:** `/parent/fees/{childId}` (parent view)
**URL:** `/accountant/fees` (accountant view)

**Display:**
- Total fee amount
- Amount paid
- Balance amount
- Due date
- Payment status
- Payment history
- Invoice list
- Download invoice button
- Pay online button (if available)

---

### 9.3 Payment Entry
**URL:** `/accountant/fees/payment`

**Form Fields:**
- Student selection
- Amount
- Payment method (dropdown: Cash, Check, Card, Transfer)
- Transaction ID
- Payment date
- Notes

**Validation:**
- Amount <= Outstanding balance
- Date <= Today

---

### 9.4 Invoice Generation
**URL:** `/accountant/invoices`

**Features:**
- Generate invoice
- Email invoice
- Print invoice
- Invoice history
- Filter by student, date range
- Bulk email invoices

---

## 10. Notification & Messaging Pages

### 10.1 Notifications
**URL:** `/notifications`

**Features:**
- Notification list
- Mark as read
- Filter (read, unread, type)
- Delete notification
- Archive notifications
- Notification preferences link

**Notification Types:**
- Attendance alerts
- Exam schedules
- Result publication
- Fee reminders
- Messages
- Announcements

---

### 10.2 Messages
**URL:** `/messages`

**Features:**
- Inbox view
- Compose message
- Reply to message
- Forward message
- Delete message
- Search messages
- Conversation view

---

### 10.3 Announcements
**URL:** `/announcements` (view)
**URL:** `/admin/announcements/create` (create)

**Features:**
- Announcement list
- View full announcement
- Create announcement (admin)
- Target audience selection
- Publish date
- Pin important announcements

---

## 11. Reports Pages

### 11.1 Dashboard Reports
**URL:** `/reports/dashboard`

**Available Reports:**
- Attendance report
- Performance report
- Fee collection report
- Enrollment report
- Leave report

---

### 11.2 Custom Report Builder
**URL:** `/reports/custom`

**Features:**
- Select report type
- Choose date range
- Select filters (class, subject, status)
- Choose metrics
- Select output format (PDF, Excel, CSV)
- Generate report
- Schedule report (admin)

---

### 11.3 Report Export
**Features:**
- PDF export
- Excel export
- CSV export
- Email export
- Print report

---

## 12. Admin Pages

### 12.1 User Management
**URL:** `/admin/users`

**Features:**
- User list
- Create user
- Edit user
- Delete user
- Assign roles
- Reset password
- Block/Unblock user
- Search & filter

---

### 12.2 Role Management
**URL:** `/admin/roles`

**Features:**
- List roles
- Create role
- Edit role
- Delete role
- Assign permissions to role
- View role permissions

---

### 12.3 System Settings
**URL:** `/admin/settings`

**Sections:**
- General settings (school name, logo, contact)
- Academic settings (year, terms)
- Fee settings
- Notification settings
- Email configuration
- SMS configuration
- Backup settings

---

### 12.4 Backup & Recovery
**URL:** `/admin/backup`

**Features:**
- View backup history
- Create manual backup
- Schedule backups
- Restore from backup
- Delete old backups
- Backup size info

---

### 12.5 Audit Logs
**URL:** `/admin/audit-logs`

**Features:**
- View all system activities
- Filter by user, action, date
- Search logs
- Export logs
- View log details
- Real-time activity log

---

## 13. Profile Pages

### 13.1 My Profile
**URL:** `/profile`

**Features:**
- Personal information
- Contact details
- Profile photo
- Edit profile button
- Change password button
- Account security section
- Login history

---

### 13.2 Settings
**URL:** `/settings`

**Options:**
- Language preference
- Notification preferences
- Privacy settings
- Two-factor authentication
- Connected devices
- Account deletion option

---

## 14. Error Pages

### 14.1 404 Not Found
**Features:**
- Friendly error message
- Home button
- Search suggestion

### 14.2 403 Forbidden
**Features:**
- Permission denied message
- Request admin access link
- Home button

### 14.3 500 Server Error
**Features:**
- Error message
- Contact support link
- Report issue button
- Home button

---

## 15. Mobile Responsive Considerations

All pages are designed to be mobile-responsive:
- Mobile-first approach
- Touch-friendly buttons (minimum 44x44 px)
- Stacked layouts on mobile
- Collapsible navigation
- Optimized forms for mobile entry
- Mobile-optimized tables

---

## Summary

The UI comprises 50+ pages organized across different modules:
- **Public pages**: Login, registration
- **Role-specific dashboards**: 5 different dashboard views
- **Management pages**: Students, teachers, classes
- **Academic pages**: Attendance, exams, results
- **Financial pages**: Fees, payments, invoices
- **Communication pages**: Notifications, messages, announcements
- **Admin pages**: User management, settings, audit logs
- **Report pages**: Dashboard and custom reports

All pages follow consistent design patterns, usability best practices, and responsive design principles.

