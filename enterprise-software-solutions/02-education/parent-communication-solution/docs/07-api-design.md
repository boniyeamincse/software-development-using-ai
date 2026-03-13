# 07 - Parent Communication API Design

## Messaging Endpoints
- `GET /api/v1/threads`: List active conversations for the current user.
- `POST /api/v1/messages`: Send a message with auto-translation trigger.
- `GET /api/v1/history/:thread_id`: Fetch paginated chat history.

## Engagement Endpoints
- `POST /api/v1/notices/acknowledge`: Mark a school notice as read.
- `GET /api/v1/events/availability`: Fetch open interview slots for a teacher.

## Infrastructure APIs
- `POST /api/v1/device/register`: Register FCM/APNs token for push.
- `GET /api/v1/translate`: On-demand translation for a specific text block.

## Security
- **HMAC Signatures**: For validating translation callback responses.
- **Rate-Limiting**: Strict limits on institutional broadcast messages to prevent spam.
