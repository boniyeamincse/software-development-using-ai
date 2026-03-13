# 07 - Fitness & Gym API Design

## Member & Check-in
- `POST /api/v1/access/verify`: Endpoint for hardware readers to validate a tag/QR.
- `GET /api/v1/member/profile`: Retrieve personal workout and billing data.
- `POST /api/v1/member/freeze`: Initiate a membership temporary suspension.

## Booking & Scheduling
- `GET /api/v1/classes/available`: Fetch filtered class list for a specific date/branch.
- `POST /api/v1/booking/confirm`: Book a spot and trigger push notification.
- `GET /api/v1/trainers/schedule`: Retrieve personal trainer open slots.

## Retail & POS
- `POST /api/v1/shop/checkout`: Finalize an in-app purchase using saved card.

## Security
- **Dynamic Access Tokens**: QR codes in the app rotate every 30 seconds to prevent "Entry Sharing."
- **Encrypted Member PII**: Masking sensitive contact info from frontline staff.
- **Hardware HMAC Signature**: All check-in data from IoT controllers must be signed by the local gateway.

---
[← Previous: Database Design](06-database-design.md) | [Back to Index](README.md) | [Next: UI Pages →](08-ui-pages.md)
