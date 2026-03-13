# 06 - Feedback Database Design

## Core Schema Components

### 1. Reviews & Ratings
- `review_id`, `product_id` (or `location_id`), `customer_id`, `rating` (1-5), `title`, `body_text`, `status` (Published/Pending/Flagged)

### 2. Multimedia
- `media_id`, `review_id`, `url`, `type` (Image/Video), `alt_text`

### 3. Sentiment Data
- `sentiment_id`, `review_id`, `score` (-1.0 to 1.0), `detected_language`, `keywords` (JSON ARRAY)

### 4. Merchant Responses
- `response_id`, `review_id`, `user_id` (Staff), `body_text`, `timestamp`

## Key Relationships
- **One-to-Many**: One Review can have multiple Media items.
- **One-to-One**: One Review has one Sentiment profile record.
- **One-to-One**: One Staff Response per Review (standard business rule).
