# 09 - Customer Support Workflows

## The Ticket Lifecycle
1. **Ingestion**: Customer sends an email or initiates a chat.
2. **Identification**: System matches the sender's identifier to an existing customer profile.
3. **Triaging**: Automated tagger applies a priority based on keywords.
4. **Routing**: Ticket is added to the relevant queue (e.g., "Refunds").
5. **Engagement**: Agent replies using a canned response to acknowledge.
6. **Resolution**: Agent provides the answer or solution; Ticket status moves to "Solved."
7. **Feedback**: Automated CSAT survey sent to customer upon closure.

## Escalation Workflow
1. SLA timer for "First Response" expires.
2. System automatically flags the ticket in RED and pings the Manager via internal channel (e.g., Slack).
3. Manager re-assigns the ticket to a Senior Agent.
