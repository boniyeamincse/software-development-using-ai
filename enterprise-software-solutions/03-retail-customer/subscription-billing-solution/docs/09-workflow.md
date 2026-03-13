# 09 - Subscription System Workflows

## The Recurring Charge Lifecycle
1. **Trigger**: System identifies a subscription has reached the end of its billing period.
2. **Drafting**: An "Invoice Draft" is created; Coupons and metered usage are calculated.
3. **Execution**: System attempts to charge the "Default Payment Method" via the Gateway.
4. **Conclusion (Success)**: Payment marked "Paid"; Revenue recognition event triggered; Receipt emailed.
5. **Conclusion (Failure)**: "Dunning Workflow" begins; Status moves to "Past Due."

## Plan Change (Proration) Workflow
1. Customer requests an upgrade from "Basic" ($10/mo) to "Pro" ($50/mo) halfway through the month.
2. System calculates unused time on Basic ($5 credit) and remaining time on Pro ($25 charge).
3. A "Proration Invoice" for $20 is generated and charged immediately.
4. Subscription `plan_id` updated; New feature access granted.

## Metered Usage Ingestion
1. App sends metered event via API (e.g., "Customer A used 5MB of bandwidth").
2. Event is validated and written to high-speed time-series storage.
3. At the end of the month, the Billing Engine aggregates all events and calculates the final total based on tiered pricing rules.

---
[← Previous: UI Pages](08-ui-pages.md) | [Back to Index](README.md) | [Next: Technology Stack →](10-tech-stack.md)
