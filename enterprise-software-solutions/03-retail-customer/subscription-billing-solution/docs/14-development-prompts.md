# 14 - Subscription Billing Development Prompts

## Core Billing Engine
### Prompt 1: Multi-Regional Recurring Billing Store
"Design a PostgreSQL schema for a global subscription billing system. The schema must handle different tax rules per region (e.g., VAT, GST, Sales Tax), multi-currency transactions, and complex billing cycles (Daily, Weekly, Monthly, Quarterly, Annual). Implement a 'Billing Clock' that triggers charges at the start of each period."

### Prompt 2: Robust Dunning & Payment Recovery
"Develop a Node.js dunning engine that handles failed subscription payments. The engine should follow a customizable retry logic (e.g., Retry on day 1, 3, 5, 7) and automatically send 'Payment Failed' notifications with secure update links. If all retries fail, move the subscription to a 'Past Due' or 'Cancelled' state."

## Plan & Lifecycle Management
### Prompt 3: Plan Versioning & Migration API
"Create an API for versioning subscription plans. If a plan's price changes, existing subscribers should remain on their 'Legacy Plan' unless explicitly migrated. Build a migration tool for admins to bulk-move users from one plan version to another with optional 'Grace Periods'."

### Prompt 4: Pro-rated Upgrade/Downgrade Logic
"Implement the logic for calculating pro-rated charges when a user changes plans mid-cycle. Handle 'Credits' (unused time on old plan) and 'Immediate Charges' (remaining time on new plan). Provide a detailed 'Invoice Preview' to the user before they confirm the change."

## Financial Integrity
### Prompt 5: Automated Tax Compliance Service
"Develop a service that integrates with an external tax provider (like Avalara or TaxJar) to calculate real-time taxes based on the user's billing address. Generate tax-compliant PDF invoices and store them securely for audit purposes."

### Prompt 6: Multi-Gateway Failover System
"Design a payment gateway failover architecture. If the primary gateway (e.g., Stripe) is down, automatically route the transaction through a secondary gateway (e.g., Adyen or Braintree) based on the subscription's region and currency."

## trust & Transparency
### Prompt 7: Secure Billing Portal API
"Create a secure API for a 'Member Billing Portal' where users can view their payment history, download past invoices, update credit cards, and manage their subscription status. Use short-lived 'Magic Links' or OAuth2 for authentication."

### Prompt 8: Credit & Refund Orchestrator
"Develop a module for managing manual and automated refunds and 'Account Credits'. Support 'Partial Refunds' and ensure that all financial movements are recorded in a double-entry ledger for accounting accuracy."

## Analytics & specialized Features
### Prompt 9: MRR, ARR & Churn Cohort Dashboard
"Create a data visualization service that tracks key SaaS metrics: Monthly Recurring Revenue (MRR), Annual Recurring Revenue (ARR), and Churn Rate. provide cohort analysis to visualize how long different user groups stay subscribed."

### Prompt 10: AI-Powered Price Optimization
"Develop a service that analyzes subscription conversion rates across different price points and regions. Provide recommendations for 'Optimal Pricing' to maximize revenue while maintaining a healthy growth rate."
