# 06 - Parent Communication Database Design

## Core Schema Components

### 1. Threads & Messages
- `thread_id`, `type` (1-to-1 / Group), `participants` (JSONB)
- `message_id`, `thread_id`, `sender_id`, `content_blob`, `translation_map` (JSONB), `timestamp`

### 2. Notices & Newsletters
- `notice_id`, `author_id`, `target_groups`, `content_html`, `read_count`

### 3. Event Bookings
- `event_id`, `teacher_id`, `slot_duration`, `availability_map`
- `booking_id`, `event_id`, `parent_id`, `start_time`

### 4. User Preferences
- `user_id`, `preferred_language`, `push_enabled`, `quiet_hours_start`, `quiet_hours_end`

## Key Relationships
- **Many-to-Many**: Users to Message Threads.
- **One-to-Many**: One User to multiple Device Tokens (for push delivery).
