# 10 - Coupon Technology Stack

## Core Engineering
- **Rule Evaluator**: Go or Rust (focused on execution speed).
- **Admin Dashboard**: React & Tailwind CSS.
- **Async Processing**: BullMQ (Node.js) or Celery (Python).

## Data & Cache
- **Master Database**: PostgreSQL.
- **Real-Time State**: Redis (for rules metadata and usage counters).
- **Search**: Elasticsearch (for searching through millions of unique codes).

## Infrastructure
- **Serverless (Optional)**: Evaluation engine deployed on AWS Lambda or Cloudflare Workers for global low-latency.
- **CDN**: Fastly for edge-caching of public (non-unique) promotion metadata.
