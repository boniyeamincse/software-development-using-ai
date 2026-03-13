# 14 - Coupon & Discount Development Prompts

## Coupon Mechanics
### Prompt 1: High-Performance Discount Engine
"Design a PostgreSQL schema for a high-concurrency discount engine. Support various discount types: 1. Percentage off, 2. Fixed amount off, 3. Buy X Get Y, 4. Free Shipping. Implement a 'Conflict Resolution' logic for when multiple coupons are applied (which one takes precedence?)."

### Prompt 2: Unique Coupon Generator
"Develop a Node.js utility that generates millions of unique, alphanumeric coupon codes. ensure that codes are easy to read (avoiding O vs 0, I vs 1), have a 'Check Digit' for basic validation, and are stored in a way that allows sub-millisecond lookup during checkout."

## specialized Rules
### Prompt 3: Dynamic Eligibility Rule Engine
"Implement a flexible rule engine that evaluates if a coupon is valid for a specific cart. Rules must support: 1. Minimum cart value, 2. Specific SKU/Category inclusion/exclusion, 3. User tier eligibility, and 4. Single-use vs. Multi-use constraints."

### Prompt 4: Geofenced & Time-Bound Discounts
"Create a service that activates discounts based on the user's current geographic location (using IP) and specific time windows (e.g., 'Flash Sale' between 2 PM and 4 PM). Handle time zone conversions accurately for a global user base."

## User Engagement
### Prompt 5: Referral Discount Orchestrator
"Design a system where users earn a discount code after referring a friend. The discount should only be activated after the friend completes their first purchase. Implement tracking for 'In-Progress Referrals' and automated distribution."

### Prompt 6: Abandoned Cart 'Save' Offer
"Develop a background worker that identifies abandoned carts. If a high-value cart is left for 4 hours, automatically generate a unique 10% discount code and send it to the user via email. Track the 'Recovery Rate' of these offers."

## Trust & Security
### Prompt 7: Coupon Abuse Prevention Filter
"Implement a security layer that detects and blocks 'Coupon Gaming' (e.g., a user creating multiple accounts to reuse a single-use code). include rate-limiting for coupon attempts to prevent brute-force attacks."

### Prompt 8: Audit Log for Manual Promotions
"Design an admin interface for creating and managing promotions. Every action (creation, deletion, or manual distribution of codes) must be recorded in an immutable audit log with the admin's ID and reason."

## Analytics & specialized Features
### Prompt 9: Promotion ROI & Conversion Report
"Create a data analytics tool that calculates the 'Revenue Impact' and 'Margin Impact' of different discount campaigns. provide insights into which coupon types result in the highest 'Customer Lifetime Value'."

### Prompt 10: AI-Powered Discount Recommender
"Develop a machine learning model that suggests the 'Minimum Effective Discount' to convert a specific user. For example, if a user is likely to buy with 5% off, do not offer them 20% off. Optimize for overall margin."

---
[← Previous: Roadmap & Future Enhancements](13-future-features.md) | [Back to Index](README.md) | [Next: Task Status →](15-task-status.md)
