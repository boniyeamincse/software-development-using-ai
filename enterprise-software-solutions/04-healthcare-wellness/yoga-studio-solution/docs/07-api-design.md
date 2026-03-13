# 07 - Yoga Studio API Design

## Student & Pass Management
- `GET /api/v1/student/profile`: Retrieve personal pass credits and booking history.
- `POST /api/v1/passes/purchase`: Finalize a class-pack or membership buy.
- `GET /api/v1/student/waiver`: Check if a student has signed the latest legal agreement.

## Class & Booking Orchestration
- `GET /api/v1/schedule/view`: Fetch all classes for a specific date range and filter.
- `POST /api/v1/booking/reserve`: Create a class reservation and deduct credit.
- `PATCH /api/v1/check-in/self`: Allow student to self-verify attendance via GPS/QR.

## Community & Content
- `GET /api/v1/community/feed`: Retrieve latest studio posts and updates.
- `POST /api/v1/messaging/send`: Send a direct message to a teacher/staff member.

## Security
- **Strict PII Redaction**: Karma/Front Desk staff only see "Names" and "Active Passes"—no home addresses or phone numbers.
- **Biometric App Lock**: Optional Fingerprint/FaceID for the student app.
- **JWT Authentication**: Secure, short-lived session management for mobile and web.
