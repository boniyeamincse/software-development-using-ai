# 06 - Appointment Database Design

## Core Schema Components

### 1. Services
- `service_id`, `title`, `duration_minutes`, `price`, `category_id`, `required_resources` (JSON)

### 2. Staff & Availability
- `staff_id`, `name`, `specialty_id`
- `availability_id`, `staff_id`, `day_of_week`, `start_time`, `end_time`

### 3. Bookings
- `booking_id`, `customer_id`, `staff_id`, `service_id`, `slot_start`, `slot_end`, `status` (Confirmed/Pending/Canceled)

### 4. Transactions
- `transaction_id`, `booking_id`, `amount`, `payment_status`, `gateway_ref`

## Key Relationships
- **Many-to-Many**: Staff to Services (Services they are qualified to perform).
- **One-to-Many**: One Booking can have multiple Status History records.
