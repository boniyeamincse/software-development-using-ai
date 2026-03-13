# 06 - Yoga Studio Database Design

## Core Schema Components

### 1. Students & Student Passes
- `student_id`, `name`, `email`, `active_pass_id`, `waiver_signed` (Boolean)
- `pass_id`, `student_id`, `type` (10-Pack/Monthly/Intro), `expiry_date`, `remaining_credits`

### 2. Classes & Studio Schedule
- `class_id`, `name`, `teacher_id`, `room_id`, `start_time`, `end_time`
- `capacity`, `current_bookings_count`, `difficulty_level`

### 3. Bookings & Attendance
- `booking_id`, `class_id`, `student_id`, `status` (Resrv/Waitlist/Cxl/Attended)
- `check_in_method` (QR/Manual/Self), `timestamp`

### 4. Retail POS & Inventory
- `item_id`, `category` (Apparel/Gear/Food), `name`, `stock_level`, `price`
- `order_id`, `student_id`, `total_amount`, `payment_method`

### 5. Community Feed & Messages
- `post_id`, `author_id`, `content_txt`, `publish_date`
- `msg_id`, `sender_id`, `recipient_id`, `body_txt`, `is_read`

## Key Relationships
- **One-to-Many**: One Student can hold multiple historical Student Passes.
- **Many-to-Many**: Students can book many Classes; Classes have many Student attendees.
- **Many-to-One**: Many Classes are taught by one specific Teacher.
- **One-to-Many**: One Studio can manage multiple physical Rooms/Zones.
