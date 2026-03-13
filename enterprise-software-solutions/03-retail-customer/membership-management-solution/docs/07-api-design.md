# 07 - Membership API Design

## Member Portal APIs
- `GET /api/v1/member/profile`: Fetch current plan and status.
- `POST /api/v1/member/update-payment`: Securely update credit card details via token exchange.
- `GET /api/v1/member/digital-token`: Generate a dynamic, time-limited QR code for access.

## Operations & Staff
- `GET /api/v1/admin/members`: Search and filter member base.
- `PATCH /api/v1/membership/freeze`: Pause a membership for a specific duration.

## Physical Integration (IoT)
- `POST /api/v1/gate/authorize`: Verify a QR/RFID token against active member status.
- `GET /api/v1/gate/sync`: Ingest latest access-control rules for offline mode.

## Security
- **Dynamic QR Codes**: Tokens that rotate every 60 seconds to prevent screenshot sharing.
- **OAuth 2.0**: For staff and member portal authentication.
