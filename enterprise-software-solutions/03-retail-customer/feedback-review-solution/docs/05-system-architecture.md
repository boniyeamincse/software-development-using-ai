# 05 - Feedback & Review Architecture

## Distributed & Analytical Design
The system follows a **Separation of Concerns** between the high-volume review ingestion engine and the heavy-lift analytical processing layer.

## Technical Infrastructure
- **Frontend**: React-based dashboard for admins; Vue.js/Svelte for lightweight widgets.
- **Backend API**: Node.js (TypeScript) or Python for managing integrations and business logic.
- **Data Pipeline**: Apache Flink or Kafka Streams for real-time sentiment analysis as reviews arrive.
- **Search & Analytics**: Elasticsearch for full-text search and faceted review filtering.

## Data Storage
- **Primary DB (PostgreSQL)**: Storing structured review data, user roles, and business metadata.
- **Object Storage (S3)**: For storing user-uploaded review photos and videos.
- **BigQuery / Snowflake**: For long-term historical sentiment trend analysis across years.
