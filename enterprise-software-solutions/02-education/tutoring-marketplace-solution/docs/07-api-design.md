# Tutoring Marketplace Solution - API Design

## 1. API Domains

1. Authentication APIs
2. User and profile APIs
3. Tutor onboarding APIs
4. Discovery and search APIs
5. Availability APIs
6. Booking APIs
7. Session APIs
8. Messaging APIs
9. Payment and payout APIs
10. Review APIs
11. Admin and compliance APIs
12. Reporting APIs

## 2. Representative Endpoint Groups

- `POST /auth/register`
- `POST /auth/login`
- `GET /tutors`
- `GET /tutors/{id}`
- `POST /tutors/{id}/availability`
- `POST /bookings`
- `POST /bookings/{id}/confirm`
- `POST /sessions/{id}/complete`
- `POST /payments/checkout`
- `POST /payouts/request`
- `POST /reviews`
- `POST /admin/tutors/{id}/approve`

## 3. API Design Rules

- Use role-aware authorization at the resource level.
- Make booking and payment endpoints idempotent.
- Emit events for booking, payment, refund, and session completion.
- Capture audit metadata for every moderation and finance action.

---
[← Previous: Database Design](06-database-design.md) | [Back to Index](README.md) | [Next: UI Pages →](08-ui-pages.md)
