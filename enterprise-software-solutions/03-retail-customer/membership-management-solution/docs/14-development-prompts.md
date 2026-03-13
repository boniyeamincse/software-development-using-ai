# 14 - Membership Management Development Prompts

## Subscription & Plan Orchestration
### Prompt 1: Flexible Membership Schema
"Design a PostgreSQL schema for a multi-tiered membership system. Include support for different billing cycles (Monthly, Annual), grace periods for failed payments, and specific 'Feature Flags' linked to each tier. Implement a 'Plan Switching' logic that handles pro-rated upgrades and downgrades."

### Prompt 2: Robust Recurring Billing Engine
"Develop a Node.js recurring billing engine that integrates with Stripe or Braintree. The engine must handle credit card expirations, implement a 'Retry Strategy' for failed charges (Dunning management), and automatically generate professional tax-compliant invoices for every transaction."

## Access & Permissions
### Prompt 3: Real-time Entitlement Enforcement
"Implement a high-performance middleware that checks a user's membership status and specific 'Entitlements' before allowing access to premium content or features. Use Redis to cache membership status with a short TTL for sub-millisecond lookups."

### Prompt 4: Multi-User / Family Plan Handler
"Create an API for managing 'Family' or 'Corporate' plans where one primary account pays for multiple sub-accounts. Include logic for 'Member Invites', role management within the group, and centralized billing."

## Content & Benefits
### Prompt 5: Member-Only Content Gateway
"Design a secure gateway for digital content (Video, PDF, Downloads) that only allows access to authenticated members with the correct tier. Use signed URLs (S3/CloudFront) to prevent direct link sharing."

### Prompt 6: Perk & Benefit Redemption Tracker
"Develop a module that tracks specialized 'Member Perks' (e.g., '1 Free Coffee per Month' or 'Access to Gym'). Implement a 'Usage Limit' engine that resets periodically and provides a clean UI for members to see their available benefits."

## Engagement & Retention
### Prompt 7: Automated Churn Prevention Workflow
"Implement an automated workflow for 'At-Risk' memberships. Trigger personalized 'Win-back' emails if a user cancels their auto-renewal or if their engagement metrics drop below a certain threshold. Include support for 'Save Offers' (e.g., 50% off for 3 months)."

### Prompt 8: Member Community & Directory API
"Create a secure API for a searchable member directory. Support privacy toggles where members can choose what info is visible to others and implement a 'Member-to-Member' messaging system (opt-in only)."

## Analytics & specialized Features
### Prompt 9: MRR & Retention Cohort Analysis
"Create a financial reporting service that calculates Monthly Recurring Revenue (MRR), Churn Rate, and 'Expansion Revenue'. Provide cohort analysis reports to see how different sign-up months are performing over time."

### Prompt 10: AI-Powered Membership Personalization
"Develop a service that recommends the 'Next Best Plan' to a user based on their usage patterns (e.g., if they are using 90% of their current tier's limits, suggest an upgrade). Provide personalized content recommendations for members."

---
[← Previous: Roadmap & Future Enhancements](13-future-features.md) | [Back to Index](README.md) | [Next: Task Status →](15-task-status.md)
