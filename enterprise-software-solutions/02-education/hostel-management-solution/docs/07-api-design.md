# Hostel Management Solution - API Design

## 🔌 API Overview

RESTful API with 100+ endpoints organized by resource type.

---

## Room Management Endpoints

**GET /api/v1/rooms** - List all rooms
**POST /api/v1/rooms** - Create room
**GET /api/v1/rooms/{id}** - Get room details
**PUT /api/v1/rooms/{id}** - Update room
**DELETE /api/v1/rooms/{id}** - Delete room
**GET /api/v1/rooms/available** - Get available rooms
**GET /api/v1/rooms/{id}/maintenance** - Get maintenance history
**POST /api/v1/rooms/{id}/maintenance** - Add maintenance record

---

## Student Management Endpoints

**GET /api/v1/students** - List students
**POST /api/v1/students** - Register student
**GET /api/v1/students/{id}** - Get student details
**PUT /api/v1/students/{id}** - Update student
**DELETE /api/v1/students/{id}** - Delete student
**GET /api/v1/students/{id}/profile** - Get student profile
**PUT /api/v1/students/{id}/profile** - Update profile
**GET /api/v1/students/{id}/documents** - Get documents
**POST /api/v1/students/{id}/documents** - Upload document
**GET /api/v1/students/{id}/emergency-contacts** - Get emergency contacts
**POST /api/v1/students/{id}/emergency-contacts** - Add emergency contact

---

## Room Allocation Endpoints

**GET /api/v1/allocations** - List allocations
**POST /api/v1/allocations** - Create allocation
**GET /api/v1/allocations/{id}** - Get allocation details
**PUT /api/v1/allocations/{id}** - Update allocation
**DELETE /api/v1/allocations/{id}** - Delete allocation
**POST /api/v1/allocations/auto-allocate** - Auto-allocate rooms
**GET /api/v1/allocations/student/{id}** - Get student allocation
**POST /api/v1/allocations/{id}/reassign** - Reassign room

---

## Billing Endpoints

**GET /api/v1/fees** - List fee structures
**POST /api/v1/fees** - Create fee structure
**GET /api/v1/fees/{id}** - Get fee details
**PUT /api/v1/fees/{id}** - Update fee
**GET /api/v1/students/{id}/fees** - Get student fees
**POST /api/v1/students/{id}/fees/assign** - Assign fees
**GET /api/v1/invoices** - List invoices
**POST /api/v1/invoices** - Create invoice
**GET /api/v1/invoices/{id}** - Get invoice details
**POST /api/v1/invoices/{id}/send** - Send invoice
**GET /api/v1/payments** - List payments
**POST /api/v1/payments** - Record payment
**GET /api/v1/payments/{id}** - Get payment details
**POST /api/v1/payments/{id}/refund** - Process refund

---

## Maintenance Endpoints

**GET /api/v1/maintenance-requests** - List requests
**POST /api/v1/maintenance-requests** - Create request
**GET /api/v1/maintenance-requests/{id}** - Get request details
**PUT /api/v1/maintenance-requests/{id}** - Update request
**DELETE /api/v1/maintenance-requests/{id}** - Delete request
**GET /api/v1/work-orders** - List work orders
**POST /api/v1/work-orders** - Create work order
**GET /api/v1/work-orders/{id}** - Get work order details
**PUT /api/v1/work-orders/{id}** - Update work order
**POST /api/v1/work-orders/{id}/complete** - Complete work order
**GET /api/v1/assets** - List assets
**POST /api/v1/assets** - Create asset
**GET /api/v1/assets/{id}** - Get asset details
**PUT /api/v1/assets/{id}** - Update asset

---

## Visitor Management Endpoints

**GET /api/v1/visitors** - List visitors
**POST /api/v1/visitors** - Register visitor
**GET /api/v1/visitors/{id}** - Get visitor details
**PUT /api/v1/visitors/{id}** - Update visitor
**GET /api/v1/visitor-passes** - List passes
**POST /api/v1/visitor-passes** - Generate pass
**GET /api/v1/visitor-passes/{id}** - Get pass details
**PUT /api/v1/visitor-passes/{id}** - Update pass
**POST /api/v1/visitor-passes/{id}/check-in** - Check in visitor
**POST /api/v1/visitor-passes/{id}/check-out** - Check out visitor
**GET /api/v1/access-logs** - Get access logs
**GET /api/v1/security-incidents** - List incidents
**POST /api/v1/security-incidents** - Report incident

---

## Attendance Endpoints

**GET /api/v1/attendance** - List attendance
**POST /api/v1/attendance/mark** - Mark attendance
**GET /api/v1/attendance/student/{id}** - Get student attendance
**GET /api/v1/attendance/reports** - Get attendance reports
**GET /api/v1/leave-requests** - List leave requests
**POST /api/v1/leave-requests** - Submit leave request
**GET /api/v1/leave-requests/{id}** - Get request details
**PUT /api/v1/leave-requests/{id}** - Update request
**POST /api/v1/leave-requests/{id}/approve** - Approve leave
**POST /api/v1/leave-requests/{id}/reject** - Reject leave

---

## Communication Endpoints

**GET /api/v1/announcements** - List announcements
**POST /api/v1/announcements** - Create announcement
**GET /api/v1/announcements/{id}** - Get announcement
**PUT /api/v1/announcements/{id}** - Update announcement
**DELETE /api/v1/announcements/{id}** - Delete announcement
**GET /api/v1/notifications** - List notifications
**POST /api/v1/notifications** - Send notification
**GET /api/v1/notifications/{id}** - Get notification
**PUT /api/v1/notifications/{id}/read** - Mark as read
**GET /api/v1/messages** - List messages
**POST /api/v1/messages** - Send message
**GET /api/v1/messages/{id}** - Get message
**PUT /api/v1/messages/{id}/read** - Mark as read

---

## Complaint Endpoints

**GET /api/v1/complaints** - List complaints
**POST /api/v1/complaints** - File complaint
**GET /api/v1/complaints/{id}** - Get complaint details
**PUT /api/v1/complaints/{id}** - Update complaint
**POST /api/v1/complaints/{id}/resolve** - Resolve complaint
**GET /api/v1/complaints/reports** - Get complaint reports

---

## Reporting Endpoints

**GET /api/v1/reports/occupancy** - Occupancy report
**GET /api/v1/reports/financial** - Financial report
**GET /api/v1/reports/maintenance** - Maintenance report
**GET /api/v1/reports/student** - Student report
**GET /api/v1/reports/visitor** - Visitor report
**GET /api/v1/reports/attendance** - Attendance report
**GET /api/v1/reports/custom** - Custom report
**POST /api/v1/reports/export** - Export report

---

## Authentication Endpoints

**POST /api/v1/auth/login** - User login
**POST /api/v1/auth/logout** - User logout
**POST /api/v1/auth/register** - User registration
**POST /api/v1/auth/refresh-token** - Refresh token
**POST /api/v1/auth/password-reset** - Reset password
**POST /api/v1/auth/2fa/enable** - Enable 2FA
**POST /api/v1/auth/2fa/verify** - Verify 2FA

---

## User Management Endpoints

**GET /api/v1/users** - List users
**POST /api/v1/users** - Create user
**GET /api/v1/users/{id}** - Get user details
**PUT /api/v1/users/{id}** - Update user
**DELETE /api/v1/users/{id}** - Delete user
**POST /api/v1/users/{id}/roles** - Assign role
**GET /api/v1/roles** - List roles
**POST /api/v1/roles** - Create role
**GET /api/v1/permissions** - List permissions

---

## API Standards

### Request Format
```json
{
  "data": {
    "field1": "value1",
    "field2": "value2"
  }
}
```

### Response Format
```json
{
  "success": true,
  "data": {...},
  "message": "Success message"
}
```

### Error Response
```json
{
  "success": false,
  "error": "Error message",
  "code": "ERROR_CODE"
}
```

---

## Authentication

- JWT tokens
- Bearer token in Authorization header
- Token expiration: 24 hours
- Refresh token: 30 days

---

## Rate Limiting

- 1000 requests per hour per user
- 10000 requests per hour per API key
- Burst limit: 100 requests per minute

---

## API Statistics

| Metric | Count |
|--------|-------|
| **Total Endpoints** | 100+ |
| **GET Endpoints** | 50+ |
| **POST Endpoints** | 30+ |
| **PUT Endpoints** | 15+ |
| **DELETE Endpoints** | 5+ |

---

**100+ endpoints for complete API coverage! 🔌**
