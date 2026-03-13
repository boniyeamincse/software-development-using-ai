# 14 - CRM Solution Development Prompts

## Lead & Contact Management
### Prompt 1: High-Performance Lead Scoring Engine
"Design a PostgreSQL schema for a lead scoring engine. The system should calculate scores based on lead activity (Email opens, Website visits, Form submissions) and firmographic data. Implement a 'Decay Algorithm' where scores decrease over time if there is no activity."

### Prompt 2: LinkedIn & Social Profile Enricher
"Develop a Node.js service that takes an email address and integrates with a third-party API (like Clearbit or Apollo) to enrich the contact profile with LinkedIn URL, Job Title, Company Size, and Industry. Handle rate-limiting and cache results for 30 days."

## Sales Pipeline & automation
### Prompt 3: Dynamic Sales Funnel Visualizer
"Create a React component that visualizes a sales pipeline as a Kanban board. Support 'Drag-and-Drop' transitions between stages (Lead, Qualification, Proposal, Negotiation, Closed). Automatically trigger an API call to record the 'Stage Duration' for bottle-neck analysis."

### Prompt 4: automated 'Sales Sequences' Engine
"Implement a background worker that executes automated sales sequences. A sequence consists of a series of scheduled emails and tasks. If a lead replies to an email, the sequence should automatically pause for that contact. Support variable interpolation (e.g., {{first_name}})."

## Interaction & Engagement
### Prompt 5: Omni-channel Communication Hub
"Design an architecture that aggregates communications from Email (IMAP), SMS (Twilio), and Voice (VoIP). Every interaction must be linked to a contact profile in a unified 'Timeline' view. Implement real-time updates using WebSockets."

### Prompt 6: AI-Driven Meeting Summary Tool
"Develop a service that accepts a meeting transcript and uses an LLM (e.g., GPT-4) to generate a concise summary, identifies key 'Sentiment', and automatically creates 'Action Items' as tasks in the CRM."

## Trust & Analytics
### Prompt 7: GDPR-Compliant Data Privacy Suite
"Implement a set of APIs for 'Right to Access' and 'Right to Erasure'. The system must provide a downloadable ZIP of all data related to a contact and support a 'Soft Delete' followed by a permanent purge after 30 days of cooling-off."

### Prompt 8: Sales Forecast Accuracy Predictor
"Build a reporting tool that compares 'Predicted Close Date' with 'Actual Close Date' across historical deals. Use a regression model to provide a 'Confidence Score' for current pipelines and alert managers to deals that are 'Stalling'."

## Intelligence & specialized Features
### Prompt 9: Executive Revenue Dashboard (KPIs)
"Create a data visualization dashboard tracking 'Customer Acquisition Cost' (CAC), 'Lifetime Value' (LTV), and 'Churn Rate'. provide monthly and quarterly comparisons with drill-down capabilities into specific sales regions."

### Prompt 10: AI Next-Best-Action (NBA) Recommender
"Develop a recommendation engine that suggests the 'Next Best Action' for a sales rep based on the deal's current state and historical success patterns (e.g., 'Recommend sending a Case Study now', 'Invite to Webinar')."

---
[← Previous: Roadmap & Future Enhancements](13-future-features.md) | [Back to Index](README.md) | [Next: Task Status →](15-task-status.md)
