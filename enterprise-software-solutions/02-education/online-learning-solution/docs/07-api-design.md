# Online Learning Solution - API Design

## 1. API Overview

**Base URL**: `https://api.onlinelearning.com/v1`

**Authentication**: JWT Bearer Token in Authorization header
```
Authorization: Bearer <token>
```

**Response Format**: JSON
**HTTP Methods**: GET, POST, PUT, DELETE, PATCH
**Status Codes**: 200 (OK), 201 (Created), 204 (No Content), 400 (Bad Request), 401 (Unauthorized), 403 (Forbidden), 404 (Not Found), 500 (Server Error)

---

## 2. Authentication Endpoints

### POST /auth/register
Register a new user account
```json
Request:
{
  "email": "student@example.com",
  "password": "SecurePass123!",
  "first_name": "John",
  "last_name": "Doe",
  "role": "student"
}

Response (201):
{
  "success": true,
  "data": {
    "user_id": "uuid",
    "email": "student@example.com",
    "role": "student"
  }
}
```

### POST /auth/login
Authenticate user and obtain tokens
```json
Request:
{
  "email": "student@example.com",
  "password": "SecurePass123!"
}

Response (200):
{
  "success": true,
  "data": {
    "access_token": "jwt_token",
    "refresh_token": "refresh_token",
    "expires_in": 3600,
    "user": {
      "id": "uuid",
      "email": "student@example.com",
      "roles": ["student"]
    }
  }
}
```

### POST /auth/refresh
Refresh access token using refresh token
```json
Request:
{
  "refresh_token": "refresh_token"
}

Response (200):
{
  "success": true,
  "data": {
    "access_token": "new_jwt_token",
    "expires_in": 3600
  }
}
```

### POST /auth/logout
Logout user
```
Response (200): { "success": true }
```

### POST /auth/forgot-password
Request password reset
```json
Request:
{
  "email": "student@example.com"
}

Response (200):
{
  "success": true,
  "message": "Password reset link sent to email"
}
```

### POST /auth/reset-password
Reset password with token
```json
Request:
{
  "token": "reset_token",
  "new_password": "NewSecurePass123!"
}

Response (200):
{
  "success": true,
  "message": "Password reset successfully"
}
```

---

## 3. User Management Endpoints

### GET /users/profile
Get current user's profile
```
Response (200):
{
  "success": true,
  "data": {
    "id": "uuid",
    "email": "student@example.com",
    "first_name": "John",
    "last_name": "Doe",
    "avatar_url": "https://...",
    "bio": "I love learning",
    "roles": ["student"],
    "created_at": "2024-03-11T10:00:00Z"
  }
}
```

### PUT /users/profile
Update current user's profile
```json
Request:
{
  "first_name": "John",
  "last_name": "Doe",
  "bio": "Updated bio",
  "timezone": "America/New_York"
}

Response (200): Updated user object
```

### PUT /users/password
Change password
```json
Request:
{
  "current_password": "OldPass123!",
  "new_password": "NewPass123!"
}

Response (200):
{
  "success": true,
  "message": "Password changed successfully"
}
```

### GET /users/{userId}
Get user profile by ID (admin only)
```
Response (200): User object
```

### GET /users
List all users (admin only, paginated)
```
Query params: ?page=1&limit=20&role=student&status=active

Response (200):
{
  "success": true,
  "data": [user_objects],
  "pagination": {
    "page": 1,
    "limit": 20,
    "total": 500,
    "total_pages": 25
  }
}
```

---

## 4. Course Management Endpoints

### GET /courses
List all courses (paginated, filterable)
```
Query params: ?page=1&limit=20&category=programming&level=beginner&search=python

Response (200):
{
  "success": true,
  "data": [course_objects],
  "pagination": {...}
}
```

### POST /courses
Create new course (instructor/admin)
```json
Request:
{
  "title": "Python Basics",
  "description": "Learn Python fundamentals",
  "category_id": "uuid",
  "level": "beginner",
  "estimated_duration_hours": 20,
  "price": 49.99
}

Response (201): Course object with id
```

### GET /courses/{courseId}
Get course details
```
Response (200): Course object with modules, sections, lessons
```

### PUT /courses/{courseId}
Update course (instructor/admin)
```json
Request: Updated course fields
Response (200): Updated course object
```

### DELETE /courses/{courseId}
Delete/archive course (admin)
```
Response (204): No content
```

### POST /courses/{courseId}/publish
Publish course (instructor/admin)
```
Response (200):
{
  "success": true,
  "message": "Course published successfully"
}
```

---

## 5. Enrollment Endpoints

### POST /enrollments
Enroll student in course
```json
Request:
{
  "course_id": "uuid"
}

Response (201):
{
  "success": true,
  "data": {
    "enrollment_id": "uuid",
    "course_id": "uuid",
    "student_id": "uuid",
    "status": "enrolled",
    "enrollment_date": "2024-03-11T10:00:00Z"
  }
}
```

### GET /enrollments
Get student's enrollments
```
Query params: ?status=enrolled&page=1&limit=10

Response (200):
{
  "success": true,
  "data": [enrollment_objects],
  "pagination": {...}
}
```

### GET /enrollments/{enrollmentId}
Get enrollment details
```
Response (200): Enrollment object
```

### PUT /enrollments/{enrollmentId}
Update enrollment status
```json
Request:
{
  "status": "completed"
}

Response (200): Updated enrollment object
```

### DELETE /enrollments/{enrollmentId}
Drop/unenroll from course
```
Response (204): No content
```

### GET /courses/{courseId}/enrollments
Get course enrollments (instructor/admin)
```
Query params: ?page=1&limit=20&status=enrolled

Response (200): List of enrollments with pagination
```

---

## 6. Content Management Endpoints

### GET /lessons/{lessonId}/content
Get lesson content items
```
Response (200):
{
  "success": true,
  "data": [content_items]
}
```

### POST /lessons/{lessonId}/content
Add content to lesson (instructor)
```json
Request:
{
  "title": "Video Lecture 1",
  "content_type": "video",
  "content_url": "https://video-cdn.com/video.mp4",
  "duration_seconds": 1800,
  "sequence_order": 1
}

Response (201): Content object
```

### GET /content/{contentId}
Get content details
```
Response (200): Content object
```

### PUT /content/{contentId}
Update content (instructor)
```json
Request: Updated content fields
Response (200): Updated content object
```

### DELETE /content/{contentId}
Delete content (instructor/admin)
```
Response (204): No content
```

---

## 7. Assessment Endpoints

### GET /assessments
Get course assessments
```
Query params: ?course_id=uuid&type=quiz&page=1

Response (200): List of assessments
```

### POST /assessments
Create assessment (instructor)
```json
Request:
{
  "course_id": "uuid",
  "lesson_id": "uuid",
  "title": "Module 1 Quiz",
  "assessment_type": "quiz",
  "passing_score": 70,
  "time_limit_minutes": 30,
  "attempt_limit": 3
}

Response (201): Assessment object
```

### GET /assessments/{assessmentId}
Get assessment details
```
Response (200): Assessment with questions
```

### POST /assessments/{assessmentId}/questions
Add question to assessment (instructor)
```json
Request:
{
  "question_type": "mcq",
  "question_text": "What is 2+2?",
  "points": 5,
  "options": [
    {"option_text": "3", "is_correct": false},
    {"option_text": "4", "is_correct": true},
    {"option_text": "5", "is_correct": false}
  ]
}

Response (201): Question object
```

### POST /assessments/{assessmentId}/submit
Submit assessment responses (student)
```json
Request:
{
  "responses": [
    {
      "question_id": "uuid",
      "selected_option_id": "uuid"
    }
  ]
}

Response (200):
{
  "success": true,
  "data": {
    "submission_id": "uuid",
    "score": 85,
    "percentage": 85,
    "passed": true,
    "feedback": "Great job!"
  }
}
```

### GET /assessments/{assessmentId}/submissions
Get assessment submissions (instructor)
```
Query params: ?page=1&limit=20&student_id=uuid

Response (200): List of submissions
```

### GET /submissions/{submissionId}
Get submission details
```
Response (200): Submission with scores and feedback
```

### PUT /submissions/{submissionId}
Grade assignment submission (instructor)
```json
Request:
{
  "score": 90,
  "feedback": "Excellent work!"
}

Response (200): Updated submission
```

---

## 8. Progress & Analytics Endpoints

### GET /students/{studentId}/progress
Get student's progress across all courses
```
Response (200):
{
  "success": true,
  "data": {
    "total_courses_enrolled": 5,
    "courses_completed": 2,
    "in_progress": 3,
    "average_score": 85,
    "courses": [
      {
        "course_id": "uuid",
        "progress_percentage": 75,
        "lessons_completed": 10,
        "total_lessons": 15
      }
    ]
  }
}
```

### GET /courses/{courseId}/progress
Get course progress (student sees own, instructor sees all students)
```
Query params: ?student_id=uuid (instructor only)

Response (200): Progress data
```

### GET /courses/{courseId}/analytics
Get course analytics (instructor/admin)
```
Response (200):
{
  "success": true,
  "data": {
    "total_enrollments": 150,
    "active_students": 145,
    "completion_rate": 78,
    "average_score": 82,
    "engagement_score": 75,
    "student_performance": [...]
  }
}
```

### GET /students/{studentId}/performance
Get student performance report
```
Response (200):
{
  "success": true,
  "data": {
    "student_id": "uuid",
    "total_assessments": 15,
    "average_score": 85,
    "time_on_platform_hours": 40,
    "engagement_level": "high",
    "performance_trend": "improving"
  }
}
```

---

## 9. Discussion Endpoints

### GET /courses/{courseId}/discussions
Get course discussions
```
Query params: ?page=1&limit=20&sort=-created_at

Response (200): List of discussions
```

### POST /courses/{courseId}/discussions
Create discussion (student/instructor)
```json
Request:
{
  "topic": "How to solve Exercise 3?",
  "description": "I'm having trouble with..."
}

Response (201): Discussion object
```

### GET /discussions/{discussionId}/threads
Get discussion threads
```
Query params: ?page=1&limit=20

Response (200): List of threads
```

### POST /discussions/{discussionId}/threads
Create discussion thread (student/instructor)
```json
Request:
{
  "title": "Solution approach",
  "content": "Try this approach..."
}

Response (201): Thread object
```

### POST /threads/{threadId}/replies
Reply to discussion thread
```json
Request:
{
  "content": "Great suggestion! Let me try that."
}

Response (201): Reply object
```

---

## 10. Notification Endpoints

### GET /notifications
Get user notifications
```
Query params: ?unread=true&page=1&limit=20

Response (200):
{
  "success": true,
  "data": [notification_objects],
  "unread_count": 5
}
```

### PUT /notifications/{notificationId}/read
Mark notification as read
```
Response (200): Updated notification
```

### PUT /notifications/read-all
Mark all notifications as read
```
Response (200):
{
  "success": true,
  "message": "All notifications marked as read"
}
```

### PUT /notifications/preferences
Update notification preferences
```json
Request:
{
  "email_announcements": true,
  "email_grades": true,
  "push_notifications": true
}

Response (200): Updated preferences
```

---

## 11. Certification Endpoints

### GET /students/{studentId}/certificates
Get student certificates
```
Response (200): List of certificates
```

### GET /certificates/{certificateId}
Get certificate details
```
Response (200): Certificate object with verification token
```

### POST /certificates/verify
Verify certificate authenticity
```json
Request:
{
  "certificate_number": "CERT-2024-12345",
  "verification_token": "token"
}

Response (200):
{
  "success": true,
  "data": {
    "valid": true,
    "student_name": "John Doe",
    "course_name": "Python Basics",
    "issued_date": "2024-03-11"
  }
}
```

### GET /students/{studentId}/badges
Get earned badges
```
Response (200): List of badges
```

---

## 12. Admin Endpoints

### GET /admin/users
List all users (admin only)
```
Query params: ?page=1&limit=20&role=student&status=active&search=john

Response (200): List of users with pagination
```

### POST /admin/users
Create user (admin only)
```json
Request:
{
  "email": "teacher@example.com",
  "first_name": "Jane",
  "last_name": "Smith",
  "role": "instructor",
  "password": "InitialPass123!"
}

Response (201): User object
```

### PUT /admin/users/{userId}
Update user (admin only)
```
Response (200): Updated user object
```

### DELETE /admin/users/{userId}
Delete user (admin only)
```
Response (204): No content
```

### POST /admin/bulk-import-users
Bulk import users via CSV (admin only)
```json
Request:
{
  "csv_file": "file_data",
  "role": "student"
}

Response (200):
{
  "success": true,
  "imported": 150,
  "skipped": 5,
  "errors": [...]
}
```

### GET /admin/reports
Get system reports
```
Query params: ?type=enrollment&period=monthly

Response (200): Report data
```

### POST /admin/system-config
Update system configuration (admin only)
```json
Request:
{
  "config_key": "max_course_capacity",
  "config_value": 500
}

Response (200): Updated config
```

---

## 13. Error Responses

### Standard Error Format
```json
{
  "success": false,
  "error": {
    "code": "INVALID_INPUT",
    "message": "Validation failed",
    "details": {
      "email": ["Invalid email format"],
      "password": ["Password must be at least 8 characters"]
    }
  },
  "timestamp": "2024-03-11T10:30:00Z"
}
```

### Common Error Codes
- `INVALID_INPUT`: Validation failed
- `UNAUTHORIZED`: Authentication required
- `FORBIDDEN`: Permission denied
- `NOT_FOUND`: Resource not found
- `CONFLICT`: Resource already exists
- `RATE_LIMITED`: Too many requests
- `SERVER_ERROR`: Internal server error

---

## 14. Rate Limiting

- **Default**: 100 requests per minute per user
- **Authentication endpoints**: 10 requests per minute per IP
- **File upload**: 10 requests per minute per user
- **Response headers**: 
  - `X-RateLimit-Limit`
  - `X-RateLimit-Remaining`
  - `X-RateLimit-Reset`

---

## 15. Pagination

All list endpoints support pagination with:
- `page`: Page number (default: 1)
- `limit`: Items per page (default: 20, max: 100)
- `sort`: Sort field (default: -created_at)

Response format:
```json
{
  "data": [...],
  "pagination": {
    "page": 1,
    "limit": 20,
    "total": 500,
    "total_pages": 25
  }
}
```

