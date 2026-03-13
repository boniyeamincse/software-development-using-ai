# 07 - Wellness API Design

## Engagement & Challenges
- `GET /api/v1/challenges/active`: Fetch a list of challenges available for the user.
- `POST /api/v1/challenges/:id/join`: Enroll a user in a specific health event.
- `GET /api/v1/leaderboards/:id`: Retrieve real-time ranking data for a challenge.

## Data Ingestion
- `POST /api/v1/sync/wearable`: Inbound endpoint for device data sync.
- `GET /api/v1/health/stats`: Aggregate summary of user's activity (Daily/Weekly).

## Rewards & HRA
- `POST /api/v1/hra/submit`: Encrypted submission of health risk assessment data.
- `POST /api/v1/rewards/redeem`: Deduct points and trigger a reward fulfillment event.

## Security
- **Dynamic Scoping**: HR Admins CANNOT access individual `hra_data`. Access is limited to aggregated, anonymized metrics.
- **HMAC Signatures**: Verification of all device-originating activity data.
- **AES-256 GCM**: Encryption for all HRA and clinical coaching message payloads.
