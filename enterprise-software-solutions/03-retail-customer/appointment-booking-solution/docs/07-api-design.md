# 07 - Appointment Booking API Design

## Booking Flow
- `GET /api/v1/availability`: Query open slots based on service and staff filters.
- `POST /api/v1/booking/lock`: Temporary lock (5 mins) for a slot during checkout.
- `POST /api/v1/booking/confirm`: finalize booking after payment confirmation.

## Admin & Staff Lifecycle
- `GET /api/v1/calendar/daily`: Fetch all bookings for a specific date or staff member.
- `PATCH /api/v1/staff/roster`: Update shift timings for a provider.

## Webhooks
- `booking.created`: Sent when a new appointment is confirmed.
- `booking.rescheduled`: Sent when a customer moves their time slot.

## Security
- **API Keys**: For external websites to embed the booking widget.
- **CSRF Protection**: For the public-facing booking portal.
