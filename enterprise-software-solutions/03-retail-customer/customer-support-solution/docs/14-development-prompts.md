# 14 - Customer Support Development Prompts

## Ticket Orchestration
### Prompt 1: Multi-Channel Ticket Routing Engine
"Design a PostgreSQL schema and a Node.js routing engine that aggregates support requests from Email, Chat, Social Media, and Voice. Implement a 'Priority Scoring' algorithm based on customer tier (SLA), sentiment analysis of the message, and ticket age.Route tickets to agents with the most relevant expertise tags."

### Prompt 2: Real-time Collaborative Chat Architecture
"Implement a scalable chat system using WebSockets and Redis. Support features like agent 'Peeking' (seeing what the customer is typing), secure file attachments, and 'Transfer with Context' where an agent can pass a chat to a specialist along with internal notes."

## Automation & Efficiency
### Prompt 3: AI-Powered 'Smart Reply' Service
"Develop a service that integrates with an LLM (e.g., GPT-4) to suggest draft responses to agents. The suggestions should be trained on the company's knowledge base and past successful ticket resolutions. Include a 'Trust Score' for each suggestion."

### Prompt 4: Automatic Knowledge Base (KB) Article Generator
"Write a backend process that analyzes 'Resolved' tickets. If a specific issue is solved multiple times with the same pattern, the service should automatically draft a draft Knowledge Base article and flag it for human editorial review."

## Specialized Workflows
### Prompt 5: SLA Breach Escalation Service
"Create a background worker service that monitors ticket response and resolution times against active SLAs. If a breach is imminent (e.g., 1 hour remaining), trigger multi-level escalations (Internal Alert -> Manager Slack -> Executive Email)."

### Prompt 6: Customer Sentiment Tracking Pipeline
"Implement a data pipeline that uses NLP (Natural Language Processing) to track customer sentiment across the lifecycle of a ticket. Provide a 'Sentiment Trend' visualization per customer and per agent in the analytics dashboard."

## Trust & Privacy
### Prompt 7: Secure Redaction API for PII
"Develop an API that automatically detects and redacts Personally Identifiable Information (PII) like credit card numbers, SSNs, and passwords from support transcripts before they are stored in the permanent database for audit."

### Prompt 8: CCPA/GDPR 'Right to be Forgotten' Handler
"Implement a workflow that allows customers to request the deletion of all their support history. Ensure that the deletion is cascaded across the database, file storage, and any third-party integrations (like Zendesk or Salesforce) while maintaining anonymized stats for reporting."

## Analytics & Insights
### Prompt 9: CSAT & NPS Survey Engine
"Build an automated survey engine that triggers 24 hours after a ticket is marked 'Resolved'. Support CSAT (Customer Satisfaction) and NPS (Net Promoter Score) metrics. Correlate survey results with agent performance and average resolution time."

### Prompt 10: Agent Workload & Drift Analysis
"Create a reporting tool for support managers that analyzes agent 'Drift' (time spent in different status states like Available, Busy, After-Call Work). Provide recommendations for shift adjustments based on volume predictions."

---
[← Previous: Roadmap & Future Enhancements](13-future-features.md) | [Back to Index](README.md) | [Next: Task Status →](15-task-status.md)
