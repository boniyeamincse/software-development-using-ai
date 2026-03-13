# 07 - Feedback & Review API Design

## Submission & Management
- `POST /api/v1/reviews/submit`: Public endpoint for processing new customer feedback.
- `GET /api/v1/reviews/feed`: Fetch reviews for a specific product or store with filters.
- `POST /api/v1/reviews/:id/respond`: Staff endpoint for replying to feedback.

## Widgets & Social Proof
- `GET /api/v1/widgets/summary`: Fetch average rating and count for rich snippets.
- `GET /api/v1/widgets/top-reviews`: High-speed endpoint for website carousels.

## External Sync
- `POST /api/webhooks/google-sync`: Ingesting reviews from Google My Business.
- `PATCH /api/v1/reviews/:id/flag`: Reporting content for moderation.

## Security
- **HMAC Signing**: For widget requests to ensure data integrity.
- **Profanity Filter**: Built-in regex and AI-based filtering on submission.

---
[← Previous: Database Design](06-database-design.md) | [Back to Index](README.md) | [Next: UI Pages →](08-ui-pages.md)
