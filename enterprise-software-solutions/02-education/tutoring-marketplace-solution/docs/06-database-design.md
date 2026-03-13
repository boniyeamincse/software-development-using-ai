# Tutoring Marketplace Solution - Database Design

## 1. Core Entity Groups

### User and Identity
- users
- user_profiles
- guardian_links
- roles
- permissions
- verification_documents

### Tutor Marketplace
- tutor_profiles
- tutor_subjects
- tutor_certifications
- tutor_languages
- tutor_pricing_plans
- tutor_availability_slots

### Discovery and Booking
- search_preferences
- tutor_favorites
- booking_requests
- bookings
- booking_packages
- cancellations

### Session Delivery
- sessions
- session_attendance
- session_notes
- session_resources
- assignments

### Finance
- payment_intents
- payments
- refunds
- commissions
- tutor_wallets
- payout_requests
- payout_transactions

### Trust and Operations
- conversations
- messages
- reviews
- review_flags
- support_tickets
- disputes
- audit_logs

## 2. Key Relationship Notes

- One guardian can manage multiple learners.
- One tutor can teach many subjects and have many time slots.
- One booking can generate one or many sessions.
- One completed session can create one review window and one payout eligibility event.

---
[← Previous: System Architecture](05-system-architecture.md) | [Back to Index](README.md) | [Next: API Design →](07-api-design.md)
