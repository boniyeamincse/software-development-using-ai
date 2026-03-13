# School Management System - API Design

## 1. API Overview

The School Management System uses a **RESTful API** design with **JSON** request/response format. All API endpoints are versioned and require authentication.

### API Base URL
```
https://api.schoolmanagementsystem.com/api/v1/
```

### API Versioning
- Current Version: `v1`
- Format: `/api/v1/`
- Future versions: `/api/v2/`, `/api/v3/`, etc.

---

## 2. Authentication

### 2.1 Authentication Methods

#### Bearer Token (JWT)
```
Authorization: Bearer {jwt_token}
```

#### API Key (for integrations)
```
X-API-Key: {api_key}
```

### 2.2 Login Endpoint

#### POST /auth/login
Login with credentials and receive JWT token.

**Request:**
```json
POST /api/v1/auth/login
Content-Type: application/json

{
  "email": "user@example.com",
  "password": "securepassword",
  "remember_me": true
}
```

**Response (200 OK):**
```json
{
  "status": "success",
  "message": "Login successful",
  "data": {
    "access_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
    "refresh_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
    "expires_in": 3600,
    "token_type": "Bearer",
    "user": {
      "id": 1,
      "email": "user@example.com",
      "first_name": "John",
      "last_name": "Doe",
      "role": "Student"
    }
  }
}
```

**Error Response (401 Unauthorized):**
```json
{
  "status": "error",
  "code": 401,
  "message": "Invalid email or password"
}
```

---

## 3. API Endpoints

### 3.1 Authentication Endpoints

| Method | Endpoint | Description | Auth |
|--------|----------|-------------|------|
| POST | /auth/login | User login | ❌ |
| POST | /auth/logout | User logout | ✅ |
| POST | /auth/register | User registration | ❌ |
| POST | /auth/refresh | Refresh access token | ✅ |
| POST | /auth/forgot-password | Request password reset | ❌ |
| POST | /auth/reset-password | Reset password | ❌ |
| POST | /auth/verify-otp | Verify OTP for 2FA | ❌ |

---

### 3.2 Student Endpoints

| Method | Endpoint | Description | Auth | Role |
|--------|----------|-------------|------|------|
| GET | /students | List all students | ✅ | Admin |
| POST | /students | Create new student | ✅ | Admin |
| GET | /students/{id} | Get student details | ✅ | Student*, Admin, Teacher* |
| PUT | /students/{id} | Update student | ✅ | Student*, Admin |
| DELETE | /students/{id} | Delete student | ✅ | Admin |
| GET | /students/{id}/attendance | Get student attendance | ✅ | Student*, Parent*, Teacher |
| GET | /students/{id}/results | Get student results | ✅ | Student*, Parent*, Teacher |
| GET | /students/{id}/fees | Get student fee status | ✅ | Student*, Parent*, Accountant |
| POST | /students/bulk-import | Bulk import students | ✅ | Admin |

**GET /students**
```json
{
  "status": "success",
  "data": {
    "items": [
      {
        "id": 1,
        "roll_number": "001",
        "first_name": "John",
        "last_name": "Doe",
        "email": "john@example.com",
        "class_id": 5,
        "class_name": "Class 10-A",
        "status": "Active",
        "created_at": "2024-01-15T10:30:00Z"
      }
    ],
    "pagination": {
      "current_page": 1,
      "per_page": 20,
      "total": 150,
      "total_pages": 8
    }
  }
}
```

---

### 3.3 Teacher Endpoints

| Method | Endpoint | Description | Auth | Role |
|--------|----------|-------------|------|------|
| GET | /teachers | List all teachers | ✅ | Admin |
| POST | /teachers | Create new teacher | ✅ | Admin |
| GET | /teachers/{id} | Get teacher details | ✅ | Admin, Teacher* |
| PUT | /teachers/{id} | Update teacher | ✅ | Admin, Teacher* |
| DELETE | /teachers/{id} | Delete teacher | ✅ | Admin |
| GET | /teachers/{id}/classes | Get teacher's classes | ✅ | Teacher*, Admin |
| GET | /teachers/{id}/subjects | Get teacher's subjects | ✅ | Teacher*, Admin |

---

### 3.4 Class Endpoints

| Method | Endpoint | Description | Auth | Role |
|--------|----------|-------------|------|------|
| GET | /classes | List all classes | ✅ | Admin |
| POST | /classes | Create new class | ✅ | Admin |
| GET | /classes/{id} | Get class details | ✅ | Admin, Teacher |
| PUT | /classes/{id} | Update class | ✅ | Admin |
| DELETE | /classes/{id} | Delete class | ✅ | Admin |
| GET | /classes/{id}/students | Get class students | ✅ | Admin, Teacher |
| POST | /classes/{id}/assign-students | Assign students to class | ✅ | Admin |
| GET | /classes/{id}/timetable | Get class timetable | ✅ | Admin, Teacher, Student |

---

### 3.5 Attendance Endpoints

| Method | Endpoint | Description | Auth | Role |
|--------|----------|-------------|------|------|
| POST | /attendance/mark | Mark attendance | ✅ | Teacher, Admin |
| GET | /attendance | Get attendance records | ✅ | Admin, Teacher |
| GET | /attendance/{id} | Get attendance detail | ✅ | Admin, Teacher, Student* |
| PUT | /attendance/{id} | Update attendance | ✅ | Teacher, Admin |
| GET | /attendance/student/{studentId} | Student attendance records | ✅ | Student*, Parent*, Admin |
| GET | /attendance/class/{classId} | Class attendance records | ✅ | Teacher, Admin |
| GET | /attendance/reports/percentage | Attendance percentage report | ✅ | Admin, Teacher |

**POST /attendance/mark**
```json
{
  "class_id": 5,
  "attendance_date": "2024-03-11",
  "records": [
    {
      "student_id": 1,
      "status": "Present"
    },
    {
      "student_id": 2,
      "status": "Absent"
    },
    {
      "student_id": 3,
      "status": "Leave",
      "remarks": "Medical leave"
    }
  ]
}
```

---

### 3.6 Examination Endpoints

| Method | Endpoint | Description | Auth | Role |
|--------|----------|-------------|------|------|
| GET | /exams | List exams | ✅ | Admin |
| POST | /exams | Create exam | ✅ | Admin |
| GET | /exams/{id} | Get exam details | ✅ | Admin, Teacher |
| PUT | /exams/{id} | Update exam | ✅ | Admin |
| DELETE | /exams/{id} | Delete exam | ✅ | Admin |
| GET | /exams/{id}/admit-cards | Get admit cards | ✅ | Admin, Student* |
| POST | /exams/{id}/generate-admit-cards | Generate admit cards | ✅ | Admin |
| GET | /exams/class/{classId} | Get class exams | ✅ | Teacher, Student* |

---

### 3.7 Result Endpoints

| Method | Endpoint | Description | Auth | Role |
|--------|----------|-------------|------|------|
| GET | /results | List results | ✅ | Admin |
| POST | /results | Create/Enter result | ✅ | Teacher, Admin |
| GET | /results/{id} | Get result details | ✅ | Admin, Teacher, Student* |
| PUT | /results/{id} | Update result | ✅ | Teacher, Admin |
| DELETE | /results/{id} | Delete result | ✅ | Admin |
| POST | /results/publish | Publish results | ✅ | Admin |
| GET | /results/student/{studentId} | Student results | ✅ | Student*, Parent*, Admin |
| GET | /results/reports/performance | Performance report | ✅ | Admin, Teacher |
| GET | /results/{id}/transcript | Generate transcript | ✅ | Student*, Parent*, Admin |

**POST /results**
```json
{
  "exam_id": 10,
  "marks": [
    {
      "student_id": 1,
      "marks_obtained": 85,
      "status": "Pass"
    },
    {
      "student_id": 2,
      "marks_obtained": 45,
      "status": "Fail"
    }
  ]
}
```

---

### 3.8 Fee Endpoints

| Method | Endpoint | Description | Auth | Role |
|--------|----------|-------------|------|------|
| GET | /fees/structures | List fee structures | ✅ | Admin |
| POST | /fees/structures | Create fee structure | ✅ | Admin |
| GET | /fees/student/{studentId} | Student fee status | ✅ | Student*, Parent*, Accountant |
| GET | /fees/student/{studentId}/invoices | Student invoices | ✅ | Student*, Parent*, Accountant |
| POST | /fees/payments | Record payment | ✅ | Accountant, Admin |
| GET | /fees/payments/{id} | Get payment details | ✅ | Accountant, Admin |
| POST | /fees/refunds | Process refund | ✅ | Accountant, Admin |
| GET | /fees/reports/collection | Fee collection report | ✅ | Accountant, Admin |

**POST /fees/payments**
```json
{
  "student_fee_id": 50,
  "amount": 5000,
  "payment_method": "Credit Card",
  "transaction_id": "TXN123456",
  "paid_date": "2024-03-11"
}
```

---

### 3.9 Notification Endpoints

| Method | Endpoint | Description | Auth | Role |
|--------|----------|-------------|------|------|
| GET | /notifications | Get my notifications | ✅ | All |
| GET | /notifications/{id} | Get notification detail | ✅ | All |
| PUT | /notifications/{id}/read | Mark as read | ✅ | All |
| DELETE | /notifications/{id} | Delete notification | ✅ | All |
| POST | /notifications/send | Send notification | ✅ | Admin |
| GET | /notifications/preferences | Get preferences | ✅ | All |
| PUT | /notifications/preferences | Update preferences | ✅ | All |

---

### 3.10 Reporting Endpoints

| Method | Endpoint | Description | Auth | Role |
|--------|----------|-------------|------|------|
| GET | /reports/attendance | Attendance report | ✅ | Admin, Teacher |
| GET | /reports/performance | Performance report | ✅ | Admin, Teacher |
| GET | /reports/fees | Fee collection report | ✅ | Accountant, Admin |
| GET | /reports/enrollment | Enrollment report | ✅ | Admin |
| POST | /reports/custom | Generate custom report | ✅ | Admin |
| GET | /reports/{id}/export | Export report | ✅ | Admin |

---

### 3.11 Holiday & Calendar Endpoints

| Method | Endpoint | Description | Auth | Role |
|--------|----------|-------------|------|------|
| GET | /calendars | List academic calendars | ✅ | All |
| POST | /calendars | Create calendar | ✅ | Admin |
| GET | /holidays | List holidays | ✅ | All |
| POST | /holidays | Create holiday | ✅ | Admin |
| GET | /events | List events | ✅ | All |
| POST | /events | Create event | ✅ | Admin |

---

### 3.12 User Management Endpoints (Admin Only)

| Method | Endpoint | Description | Auth | Role |
|--------|----------|-------------|------|------|
| GET | /users | List users | ✅ | Admin |
| POST | /users | Create user | ✅ | Admin |
| GET | /users/{id} | Get user details | ✅ | Admin, User* |
| PUT | /users/{id} | Update user | ✅ | Admin, User* |
| DELETE | /users/{id} | Delete user | ✅ | Admin |
| POST | /users/{id}/assign-role | Assign role | ✅ | Admin |
| POST | /users/{id}/reset-password | Reset password | ✅ | Admin |

---

## 4. Standard Response Format

### Success Response (2xx)
```json
{
  "status": "success",
  "code": 200,
  "message": "Operation successful",
  "data": {
    // Actual data
  },
  "timestamp": "2024-03-11T10:30:00Z"
}
```

### Error Response (4xx, 5xx)
```json
{
  "status": "error",
  "code": 400,
  "message": "Invalid request",
  "errors": {
    "field_name": ["Error message 1", "Error message 2"]
  },
  "timestamp": "2024-03-11T10:30:00Z"
}
```

---

## 5. Error Codes

| Code | Status | Description |
|---|---|---|
| 200 | OK | Request successful |
| 201 | Created | Resource created successfully |
| 204 | No Content | Request successful, no content |
| 400 | Bad Request | Invalid input or missing required fields |
| 401 | Unauthorized | Authentication required or failed |
| 403 | Forbidden | User doesn't have permission |
| 404 | Not Found | Resource not found |
| 409 | Conflict | Resource already exists or conflict |
| 422 | Unprocessable Entity | Validation failed |
| 429 | Too Many Requests | Rate limit exceeded |
| 500 | Internal Server Error | Server error |
| 503 | Service Unavailable | Service temporarily unavailable |

---

## 6. Pagination

All list endpoints support pagination:

**Query Parameters:**
- `page`: Page number (default: 1)
- `per_page`: Items per page (default: 20, max: 100)
- `sort`: Sort field (e.g., `created_at`, `-created_at` for descending)
- `filter`: Filter criteria (query param format)

**Example:**
```
GET /api/v1/students?page=2&per_page=25&sort=-created_at&status=Active
```

**Response includes:**
```json
{
  "data": [...],
  "pagination": {
    "current_page": 2,
    "per_page": 25,
    "total": 150,
    "total_pages": 6,
    "from": 26,
    "to": 50
  }
}
```

---

## 7. Rate Limiting

API requests are rate limited to prevent abuse:

**Headers:**
- `X-RateLimit-Limit`: Maximum requests per hour
- `X-RateLimit-Remaining`: Remaining requests
- `X-RateLimit-Reset`: Reset timestamp (Unix)

**Limits:**
- Authenticated users: 1000 requests/hour
- Public endpoints: 100 requests/hour
- File uploads: 50 requests/hour

---

## 8. Filtering & Search

### Query Parameter Filters

**Example:**
```
GET /api/v1/students?status=Active&class_id=5&search=john
```

### Advanced Filters

```
GET /api/v1/results?exam_id=10&status=Pass&percentage_gt=80
```

### Search Operators

- `_eq`: Equal
- `_neq`: Not equal
- `_gt`: Greater than
- `_gte`: Greater than or equal
- `_lt`: Less than
- `_lte`: Less than or equal
- `_like`: Contains (for strings)
- `_in`: In array

---

## 9. Sorting

Use the `sort` parameter:

```
GET /api/v1/students?sort=-created_at,first_name
```

- Prefix with `-` for descending order
- Multiple fields separated by comma

---

## 10. API Documentation Tools

- **Swagger/OpenAPI**: Available at `/api/docs`
- **Postman Collection**: Download from dashboard
- **API Explorer**: Interactive API testing at `/api/explorer`

---

## Summary

The API design follows RESTful principles with:
- Clear, resource-based endpoints
- Consistent response format
- Comprehensive error handling
- Rate limiting and pagination
- Role-based access control
- JWT authentication
- Detailed documentation

---
[← Previous: Database Design](06-database-design.md) | [Back to Index](README.md) | [Next: UI Pages →](08-ui-pages.md)
