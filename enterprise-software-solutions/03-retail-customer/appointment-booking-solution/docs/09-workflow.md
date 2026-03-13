# 09 - Appointment Booking Workflows

## The Booking Lifecycle
1. **Search**: Customer filters by service location and staff.
2. **Evaluation**: System calculates real-time overlap between staff, room, and equipment availability.
3. **Locking**: On selecting a slot, system initiates a short-term Redis lock.
4. **Validation**: Customer provides contact info and payment details.
5. **Confirmation**: Lock is transitioned to a persistent DB record; Email sent.
6. **Engagement**: 24h & 1h reminders sent; Staff portal updated.

## Rescheduling Flow
1. Customer requests a new time via portal.
2. System verifies if the new slot is open.
3. If open, old slot is released and the new one is locked.
4. Notification sent to staff member regarding the change.
