# 14 - Feedback & Review Development Prompts

## Feedback Orchestration
### Prompt 1: Multi-Model Sentiment Analysis
"Design a data pipeline that processes customer reviews using multiple NLP models (e.g., VADER, BERT). Implement a 'Consensus Score' that identifies the primary emotion (Happy, Frustrated, Neutral) and extracts key 'Topic Clusters' (e.g., 'Shipping Speed', 'Product Quality')."

### Prompt 2: Real-Time Feedback Widget
"Develop a lightweight, embeddable React widget for capturing user feedback. THe widget should support: 1. Star ratings, 2. Textual comments, 3. Image uploads, and 4. Specialized attributes (e.g., 'Size fit' for clothes). Implement a 'Honeypot' and rate-limiting to prevent spam."

## Trust & Verification
### Prompt 3: 'Verified Purchase' Logic
"Implement a service that links reviews to actual order IDs from the Ecommerce module. A review should only receive the 'Verified Purchase' badge if the associated user has a completed order for that specific SKU. Prevent duplicate reviews for the same transaction."

### Prompt 4: AI-Driven Fraudulent Review Detection
"Develop an algorithm to detect 'Review Bombing' or fraudulent patterns (e.g., 50 reviews from the same IP range in 10 minutes). Flag suspicious content for human moderator review and implement a 'Shadow Ban' logic for known malicious actors."

## Specialized Workflows
### Prompt 5: Closed-Loop Issue Resolution
"Create a workflow where 'Negative Reviews' (1 or 2 stars) automatically trigger a support ticket in the Customer Support module. Implement a 'Recovery Tracker' that monitors if the customer updates their review after the support team resolves the issue."

### Prompt 6: Dynamic Survey Branching Logic
"Build a survey engine where questions change based on previous answers (e.g., 'If rating < 3, ask: What specifically could we improve?'). Store the entire survey tree in a flexible JSON format and provide a builder UI for admins."

## Engagement & Rewards
### Prompt 7: Incentivized Feedback Engine
"Develop a system that automatically sends 'Review Coupons' to customers after they submit their first photo/video review. Implement logic to prevent 'Reward Gaming' where users submit low-quality content just for the prize."

### Prompt 8: Social Proof Widget (UGC)
"Create a UI component that displays User-Generated Content (UGC) - like customer photos and videos - on the product page. Implement a 'Moderator Approval' queue where admins can curate which content is displayed."

## Analytics & Reporting
### Prompt 9: Brand Sentiment Dashboard
"Create a data visualization service that tracks Net Promoter Score (NPS) and Customer Satisfaction (CSAT) trends over time. Provide 'Word Clouds' of the most common positive and negative terms found in recent reviews."

### Prompt 10: Product Improvement Recommendations
"Develop an AI service that analyzes thousands of reviews and provides actionable advice for product development (e.g., '80% of negative reviews for the Large size say it runs small; recommend updating the size guide')."
