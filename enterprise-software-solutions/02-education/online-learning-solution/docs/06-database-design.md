# Online Learning Solution - Database Design

## 1. Database Overview

**Primary Database**: PostgreSQL (relational database)
**Alternative**: MySQL
**Total Tables**: 60+ core tables
**Relationships**: Foreign key constraints with ON DELETE CASCADE
**Indexing**: Strategic indexes for performance optimization
**Replication**: Master-slave setup for high availability

---

## 2. User & Authentication Tables

### users
```sql
users
├── id (PK, UUID)
├── email (UNIQUE)
├── username (UNIQUE)
├── password_hash
├── first_name
├── last_name
├── phone
├── avatar_url
├── status (active, inactive, suspended)
├── last_login
├── created_at
├── updated_at
├── deleted_at (soft delete)
```

### user_profiles
```sql
user_profiles
├── id (PK, UUID)
├── user_id (FK)
├── bio
├── organization
├── country
├── timezone
├── language_preference
├── profile_completion_percentage
├── created_at
├── updated_at
```

### user_roles
```sql
user_roles
├── id (PK, UUID)
├── user_id (FK)
├── role_id (FK)
├── assigned_by
├── assigned_at
├── expires_at (optional)
├── created_at
```

### roles
```sql
roles
├── id (PK, UUID)
├── name (UNIQUE: student, instructor, admin, etc.)
├── description
├── created_at
├── updated_at
```

### permissions
```sql
permissions
├── id (PK, UUID)
├── name (UNIQUE)
├── description
├── resource
├── action
├── created_at
```

### role_permissions
```sql
role_permissions
├── role_id (FK)
├── permission_id (FK)
├── created_at
├── INDEX: (role_id, permission_id)
```

### login_history
```sql
login_history
├── id (PK, UUID)
├── user_id (FK)
├── login_time
├── logout_time
├── ip_address
├── user_agent
├── success (boolean)
├── created_at
├── INDEX: (user_id, login_time)
```

### password_resets
```sql
password_resets
├── id (PK, UUID)
├── user_id (FK)
├── token (UNIQUE)
├── expires_at
├── created_at
├── used_at
```

---

## 3. Course Management Tables

### courses
```sql
courses
├── id (PK, UUID)
├── title
├── description
├── slug (UNIQUE)
├── instructor_id (FK → users)
├── category_id (FK)
├── status (draft, published, archived)
├── visibility (public, private, restricted)
├── thumbnail_url
├── banner_url
├── level (beginner, intermediate, advanced)
├── language
├── start_date
├── end_date
├── max_students (NULL for unlimited)
├── price (decimal, NULL for free)
├── estimated_duration_hours
├── credits
├── created_at
├── updated_at
├── deleted_at
├── INDEX: (instructor_id, status)
├── INDEX: (category_id, visibility)
```

### course_categories
```sql
course_categories
├── id (PK, UUID)
├── name (UNIQUE)
├── slug (UNIQUE)
├── description
├── parent_category_id (FK, self-referential)
├── icon_url
├── created_at
├── updated_at
```

### course_modules
```sql
course_modules
├── id (PK, UUID)
├── course_id (FK)
├── title
├── description
├── sequence_order
├── status (draft, published)
├── created_at
├── updated_at
├── INDEX: (course_id, sequence_order)
```

### course_sections
```sql
course_sections
├── id (PK, UUID)
├── module_id (FK)
├── title
├── description
├── sequence_order
├── status (draft, published)
├── created_at
├── updated_at
├── INDEX: (module_id, sequence_order)
```

### course_lessons
```sql
course_lessons
├── id (PK, UUID)
├── section_id (FK)
├── title
├── description
├── content_type (text, video, interactive)
├── sequence_order
├── duration_minutes
├── required_reading
├── objectives
├── status (draft, published)
├── created_at
├── updated_at
├── INDEX: (section_id, sequence_order)
```

### course_instructors
```sql
course_instructors
├── course_id (FK)
├── instructor_id (FK → users)
├── role (instructor, ta, reviewer)
├── joined_at
├── removed_at
├── PRIMARY KEY: (course_id, instructor_id)
```

---

## 4. Content Management Tables

### content_items
```sql
content_items
├── id (PK, UUID)
├── lesson_id (FK)
├── title
├── content_type (text, video, pdf, image, audio, interactive)
├── sequence_order
├── content_url
├── thumbnail_url
├── duration_seconds (for video/audio)
├── file_size
├── mime_type
├── created_by (FK → users)
├── created_at
├── updated_at
├── deleted_at
├── INDEX: (lesson_id, sequence_order)
```

### content_versions
```sql
content_versions
├── id (PK, UUID)
├── content_item_id (FK)
├── version_number
├── content_url
├── changed_by (FK → users)
├── change_description
├── created_at
```

### media_files
```sql
media_files
├── id (PK, UUID)
├── content_item_id (FK)
├── file_name
├── file_path
├── file_size
├── mime_type
├── storage_type (s3, local, azure)
├── uploaded_by (FK → users)
├── uploaded_at
├── deleted_at
```

### content_transcripts
```sql
content_transcripts
├── id (PK, UUID)
├── content_item_id (FK)
├── transcript_text
├── language
├── created_at
├── updated_at
```

### content_captions
```sql
content_captions
├── id (PK, UUID)
├── content_item_id (FK)
├── caption_url
├── language
├── format (vtt, srt, sbv)
├── created_at
```

---

## 5. Enrollment Tables

### enrollments
```sql
enrollments
├── id (PK, UUID)
├── course_id (FK)
├── student_id (FK → users)
├── status (enrolled, completed, dropped, inactive)
├── enrollment_date
├── completion_date
├── progress_percentage
├── is_auditing (boolean, for audit students)
├── created_at
├── updated_at
├── deleted_at
├── INDEX: (course_id, student_id) - UNIQUE
├── INDEX: (student_id, status)
```

### enrollment_history
```sql
enrollment_history
├── id (PK, UUID)
├── enrollment_id (FK)
├── status (previous status)
├── status_changed_to (new status)
├── changed_by (FK → users)
├── reason
├── changed_at
```

### prerequisites
```sql
prerequisites
├── id (PK, UUID)
├── course_id (FK)
├── prerequisite_course_id (FK → courses)
├── created_at
```

### waitlist
```sql
waitlist
├── id (PK, UUID)
├── course_id (FK)
├── student_id (FK → users)
├── position
├── added_at
├── removed_at
├── enrolled_at
├── PRIMARY KEY: (course_id, student_id)
```

---

## 6. Assessment Tables

### assessments
```sql
assessments
├── id (PK, UUID)
├── course_id (FK)
├── lesson_id (FK)
├── title
├── description
├── assessment_type (quiz, assignment, exam)
├── passing_score (percentage)
├── total_points
├── time_limit_minutes
├── attempt_limit
├── show_correct_answers (boolean)
├── show_answers_after (submission, completion, never)
├── shuffle_questions (boolean)
├── randomize_options (boolean)
├── status (draft, published, archived)
├── available_from
├── available_until
├── created_at
├── updated_at
├── INDEX: (course_id, status)
```

### questions
```sql
questions
├── id (PK, UUID)
├── assessment_id (FK)
├── question_bank_id (FK, optional)
├── question_type (mcq, true_false, short_answer, essay, matching, fill_in_blank)
├── question_text
├── image_url (optional)
├── points
├── difficulty_level (easy, medium, hard)
├── sequence_order
├── explanation (for answer feedback)
├── tags (JSON array)
├── created_at
├── updated_at
├── INDEX: (assessment_id, sequence_order)
```

### question_options
```sql
question_options
├── id (PK, UUID)
├── question_id (FK)
├── option_text
├── is_correct (boolean)
├── sequence_order
├── explanation (optional)
├── image_url (optional)
├── INDEX: (question_id, sequence_order)
```

### question_banks
```sql
question_banks
├── id (PK, UUID)
├── course_id (FK)
├── name
├── description
├── created_by (FK → users)
├── created_at
├── updated_at
```

### student_responses
```sql
student_responses
├── id (PK, UUID)
├── assessment_id (FK)
├── student_id (FK → users)
├── question_id (FK)
├── response_text (for short answer/essay)
├── selected_option_id (FK)
├── points_earned
├── is_correct
├── answered_at
├── time_spent_seconds
├── INDEX: (assessment_id, student_id)
├── INDEX: (student_id, answered_at)
```

### submissions
```sql
submissions
├── id (PK, UUID)
├── assessment_id (FK)
├── student_id (FK → users)
├── submission_status (in_progress, submitted, graded, returned)
├── submitted_at
├── started_at
├── score
├── points_earned
├── points_total
├── percentage
├── attempt_number
├── feedback
├── graded_by (FK → users)
├── graded_at
├── INDEX: (assessment_id, student_id)
├── INDEX: (student_id, submitted_at)
```

### assignment_submissions
```sql
assignment_submissions
├── id (PK, UUID)
├── assessment_id (FK)
├── student_id (FK → users)
├── submitted_at
├── submission_file_url
├── submission_text
├── grade
├── max_grade
├── feedback
├── graded_by (FK → users)
├── graded_at
├── late_submission (boolean)
├── plagiarism_score
├── INDEX: (assessment_id, student_id)
```

### rubrics
```sql
rubrics
├── id (PK, UUID)
├── assessment_id (FK)
├── title
├── description
├── created_by (FK → users)
├── created_at
├── updated_at
```

### rubric_criteria
```sql
rubric_criteria
├── id (PK, UUID)
├── rubric_id (FK)
├── criterion_name
├── description
├── max_points
├── sequence_order
├── INDEX: (rubric_id, sequence_order)
```

---

## 7. Progress & Tracking Tables

### lesson_completion
```sql
lesson_completion
├── id (PK, UUID)
├── lesson_id (FK)
├── student_id (FK → users)
├── started_at
├── completed_at
├── completion_percentage
├── time_spent_seconds
├── is_completed (boolean)
├── PRIMARY KEY: (lesson_id, student_id) - UNIQUE
├── INDEX: (student_id, completed_at)
```

### course_progress
```sql
course_progress
├── id (PK, UUID)
├── course_id (FK)
├── student_id (FK → users)
├── last_accessed_at
├── total_time_spent_seconds
├── lessons_completed
├── total_lessons
├── progress_percentage
├── updated_at
├── PRIMARY KEY: (course_id, student_id) - UNIQUE
```

### engagement_metrics
```sql
engagement_metrics
├── id (PK, UUID)
├── student_id (FK → users)
├── course_id (FK)
├── login_count
├── content_views
├── time_on_platform_seconds
├── assignments_submitted
├── forum_posts
├── last_activity_at
├── updated_at
```

### milestones
```sql
milestones
├── id (PK, UUID)
├── course_id (FK)
├── student_id (FK → users)
├── milestone_type (lesson_complete, module_complete, course_complete, achievement)
├── milestone_name
├── earned_at
├── created_at
```

---

## 8. Communication Tables

### discussions
```sql
discussions
├── id (PK, UUID)
├── course_id (FK)
├── topic
├── description
├── created_by (FK → users)
├── is_pinned (boolean)
├── is_closed (boolean)
├── created_at
├── updated_at
├── INDEX: (course_id, created_at)
```

### discussion_threads
```sql
discussion_threads
├── id (PK, UUID)
├── discussion_id (FK)
├── user_id (FK → users)
├── title
├── content
├── is_answer (boolean, mark as answer)
├── likes_count
├── replies_count
├── created_at
├── updated_at
├── deleted_at
├── INDEX: (discussion_id, created_at)
```

### discussion_replies
```sql
discussion_replies
├── id (PK, UUID)
├── thread_id (FK)
├── user_id (FK → users)
├── parent_reply_id (FK, self-referential for nested replies)
├── content
├── likes_count
├── created_at
├── updated_at
├── deleted_at
```

### messages
```sql
messages
├── id (PK, UUID)
├── sender_id (FK → users)
├── recipient_id (FK → users)
├── subject
├── message_body
├── is_read (boolean)
├── sent_at
├── read_at
├── created_at
├── INDEX: (recipient_id, is_read)
├── INDEX: (sender_id, sent_at)
```

### announcements
```sql
announcements
├── id (PK, UUID)
├── course_id (FK)
├── created_by (FK → users)
├── title
├── content
├── publish_date
├── expires_date (optional)
├── created_at
├── updated_at
```

### notifications
```sql
notifications
├── id (PK, UUID)
├── user_id (FK → users)
├── type (enrollment, grade, assignment, announcement, etc.)
├── title
├── message
├── related_resource_id
├── is_read (boolean)
├── created_at
├── read_at
├── INDEX: (user_id, created_at)
├── INDEX: (user_id, is_read)
```

### notification_preferences
```sql
notification_preferences
├── user_id (PK, FK → users)
├── email_announcements (boolean)
├── email_grades (boolean)
├── email_messages (boolean)
├── email_deadlines (boolean)
├── in_app_notifications (boolean)
├── push_notifications (boolean)
├── created_at
├── updated_at
```

---

## 9. Grading Tables

### grades
```sql
grades
├── id (PK, UUID)
├── student_id (FK → users)
├── assessment_id (FK)
├── course_id (FK)
├── score (points earned)
├── max_score (total points)
├── percentage
├── letter_grade (A, B, C, etc.)
├── is_final (boolean)
├── graded_at
├── created_at
├── updated_at
├── INDEX: (student_id, course_id)
├── INDEX: (assessment_id, student_id)
```

### course_grades
```sql
course_grades
├── id (PK, UUID)
├── student_id (FK → users)
├── course_id (FK)
├── final_score
├── final_percentage
├── letter_grade
├── completion_date
├── created_at
├── PRIMARY KEY: (student_id, course_id)
```

---

## 10. Certification Tables

### certificates
```sql
certificates
├── id (PK, UUID)
├── student_id (FK → users)
├── course_id (FK)
├── certificate_number (UNIQUE)
├── issue_date
├── expiry_date (optional)
├── document_url
├── verification_token
├── created_at
```

### digital_badges
```sql
digital_badges
├── id (PK, UUID)
├── student_id (FK → users)
├── badge_type (completion, achievement, skill)
├── badge_name
├── badge_image_url
├── description
├── earned_at
├── shareable (boolean)
└── created_at
```

---

## 11. Live Session Tables

### live_sessions
```sql
live_sessions
├── id (PK, UUID)
├── course_id (FK)
├── instructor_id (FK → users)
├── title
├── description
├── session_type (webinar, office_hours, group_session)
├── scheduled_start_time
├── scheduled_end_time
├── actual_start_time
├── actual_end_time
├── meeting_link
├── recording_url
├── max_participants
├── status (scheduled, in_progress, completed, cancelled)
├── created_at
├── updated_at
```

### session_attendance
```sql
session_attendance
├── session_id (FK)
├── student_id (FK → users)
├── joined_at
├── left_at
├── duration_minutes
├── attended (boolean)
├── PRIMARY KEY: (session_id, student_id)
```

---

## 12. Analytics & Reporting Tables

### analytics_data
```sql
analytics_data
├── id (PK, UUID)
├── metric_name
├── metric_value (JSON)
├── time_period (daily, weekly, monthly)
├── recorded_at
├── created_at
├── INDEX: (metric_name, time_period)
```

### course_analytics
```sql
course_analytics
├── course_id (PK, FK)
├── total_enrollments
├── active_students
├── completion_rate
├── average_score
├── engagement_score
├── updated_at
```

---

## 13. Configuration Tables

### system_config
```sql
system_config
├── id (PK, UUID)
├── config_key (UNIQUE)
├── config_value (JSON)
├── description
├── updated_at
```

### audit_logs
```sql
audit_logs
├── id (PK, UUID)
├── user_id (FK → users)
├── action (create, update, delete)
├── resource_type (course, user, assessment, etc.)
├── resource_id
├── old_values (JSON)
├── new_values (JSON)
├── ip_address
├── created_at
├── INDEX: (user_id, created_at)
├── INDEX: (resource_type, resource_id)
```

---

## 14. Indexes Strategy

### Primary Indexes
- All primary keys
- Foreign keys (for join optimization)
- (course_id, status) on courses
- (student_id, enrollment_status) on enrollments
- (instructor_id, course_id) on courses
- (user_id, created_at) on audit logs

### Composite Indexes
- (enrollment_id, student_id) on enrollments
- (assessment_id, student_id) on submissions
- (course_id, lesson_id) on lessons
- (course_id, student_id) on course_progress

### Performance Considerations
- Full-text index on course titles and descriptions
- Partial index on active enrollments (WHERE status = 'enrolled')
- Partitioned indexes for large tables (lesson_completion, engagement_metrics)

---
[← Previous: System Architecture](05-system-architecture.md) | [Back to Index](README.md) | [Next: API Design →](07-api-design.md)
