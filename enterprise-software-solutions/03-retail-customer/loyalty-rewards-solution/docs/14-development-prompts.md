# 14 - Loyalty & Rewards Development Prompts

## Points & Rewards Engine
### Prompt 1: High-Precision Points Ledger
"Design a PostgreSQL schema for a transactional loyalty points ledger. The schema must handle point accrual, redemption, and expiration (e.g., points expire after 12 months). Implement ACID-compliant transactions to ensure points are never double-counted or lost during high-concurrency events."

### Prompt 2: Dynamic Earnings Rule Engine
"Implement a flexible earnings engine in Node.js. Admins should be able to create complex rules (e.g., 'Double points on Tuesdays for Category X', '100 bonus points for your 5th purchase'). Use a rule-engine library or a custom JSON-based logic parser to evaluate transactions against active rules."

## Engagement & Tiers
### Prompt 3: Automated Tier Progression Service
"Develop a background service that evaluates user spending and activity to automatically update their 'Loyalty Tier' (e.g., Silver, Gold, Platinum). Include logic for 'Tier Downturn' if a user doesn't meet maintenance requirements within a 12-month rolling period."

### Prompt 4: Real-time Reward Catalog API
"Create an API for a reward catalog that supports various redemption types: 1. Discount Coupons, 2. Free Products, 3. Points-plus-Cash purchases, and 4. Charitable Donations. Implement real-time 'Affordability' checks based on the user's current point balance."

## Specialized Workflows
### Prompt 5: Referral & Social SHaring Tracker
"Build a module to track and reward customer referrals. Generate unique 'Referral Links', track successful conversions (linked to a first purchase), and automatically distribute rewards to both the referrer and the referee. Implement fraud protection for self-referral."

### Prompt 6: Birthday & Milestone Automation
"Develop a service that triggers special loyalty rewards and personalized notifications on user birthdays or account anniversaries. Include support for 'Early Access' to sales for top-tier members."

## Trust & Integrity
### Prompt 7: Point Forgery & Abuse Detection
"Implement a monitoring layer that detects suspicious point accrual patterns (e.g., a user earning points faster than physically possible through normal purchases). Flag abnormal accounts for manual audit and implement temporary point freezes."

### Prompt 8: Audit Log for Manual Adjustments
"Design a secure 'Admin Adjustment' interface that allows customer support to manually add or remove points (with mandatory reason codes). Every manual change must be recorded in an immutable audit log with the admin's ID and a timestamp."

## Analytics & specialized Features
### Prompt 9: Loyalty ROI & Redemption Dashboard
"Create a data visualization service that tracks 'Point Liability' (unredeemed points), 'Redemption Rate', and the impact of loyalty members on 'Lifetime Value' (LTV). Output the data for an executive dashboard."

### Prompt 10: AI-Powered 'At-Risk' Member Predictor
"Develop a machine learning model that identifies loyalty members who haven't engaged in 60+ days but were previously active. Provide a 'Churn Risk Score' and trigger a specialized 'We Miss You' reward campaign for those users."
