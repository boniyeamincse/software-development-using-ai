# 07 - API Design

## Authentication
- `POST /api/auth/login`: Authenticate user and return JWT.
- `POST /api/auth/logout`: Revoke session.

## Student Management
- `GET /api/students`: List students (with filters).
- `POST /api/students`: Create new student record.
- `GET /api/students/:id`: Detailed student profile.

## Attendance
- `POST /api/attendance/mark`: Bulk mark attendance for a class.
- `GET /api/attendance/report/:student_id`: Fetch attendance history.

## Academics
- `POST /api/exams/grades`: Submit grades for a specific subject/exam.
- `GET /api/reports/generate/:student_id`: Generate PDF report card.

## Fees
- `GET /api/fees/status/:student_id`: Check pending fee details.
- `POST /api/fees/payment`: Initiate online payment transaction.
