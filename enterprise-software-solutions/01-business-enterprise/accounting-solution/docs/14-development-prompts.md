# 14 - Accounting Solution Development Prompts

## General Ledger & Integrity
### Prompt 1: High-Precision Double-Entry Ledger
"Design a PostgreSQL schema for a double-entry accounting system. The schema must ensure that every transaction has equal debits and credits. Implement a constraint that prevents 'Out-of-Balance' entries and maintains a permanent, immutable record of every transaction ID and timestamp."

### Prompt 2: Real-time Multi-Currency Revaluation
"Develop a Node.js service that automatically revalues foreign currency accounts based on current market rates. The service should record 'Unrealized Gain/Loss' entries in the General Ledger every day at midnight and provide a report on exchange rate exposure."

## Financial Operations
### Prompt 3: automated Bank Reconciliation Service
"Implement an algorithm that matches bank statement lines (imported via CSV or OFX) with internal Ledger transactions. The logic should account for date variances, small amount discrepancies (using a 'Tolerance' setting), and suggest potential matches for manual review."

### Prompt 4: Accounts Receivable (AR) & Collection Engine
"Create a backend service for managing aging accounts. If an invoice remains unpaid after 30, 60, or 90 days, trigger automated 'Soft Reminders' and 'Final Notices'. Provide a dashboard for the collections team showing 'Days Sales Outstanding' (DSO)."

## Tax & Compliance
### Prompt 5: Multi-Regional VAT/GST Tax Calculator
"Design a service that calculates real-time Sales Tax, VAT, or GST based on the jurisdiction of both the buyer and the seller. Support specialized tax rules (e.g., zero-rated items, tax exemptions) and integrate with an external tax provider API."

### Prompt 6: SOX-Compliant Audit Transaction Vault
"Develop a secure Audit Vault that stores a hash of every financial transaction. If a transaction record is tampered with, the system should instantly alert the compliance officer and provide a detailed 'Gap Report' for the audit trail."

## specialized Workflows
### Prompt 7: Automated Fixed Asset Depreciation
"Implement a module that tracks fixed assets (Equipment, Real Estate, IT). Automatically calculate and record monthly depreciation entries using multiple methods (Straight-line, Declining balance) based on the asset's useful life."

### Prompt 8: Expense Management & Approval Hub
"Create a workflow for employee expense reimbursement. Support photo uploads for receipts, automated 'Policy Enforcement' (e.g., flagging individual meals over $50), and multi-stage managerial approval before triggering a payment."

## Analytics & specialized Features
### Prompt 9: Real-time P&L and Balance Sheet Generator
"Create a data visualization service that generates real-time Profit & Loss (P&L) statements and Balance Sheets. Provide drill-down capabilities where a user can click on a line item to see the underlying ledger transactions."

### Prompt 10: AI-Powered Fraud Detection
"Develop a machine learning model that identifies 'Anomaly Transactions' (e.g., unusual spending patterns, double-billed invoices, or payments to unrecognized vendors). Provide a 'Risk Score' for every transaction before it is finalized."

---
[← Previous: Roadmap & Future Enhancements](13-future-features.md) | [Back to Index](README.md) | [Next: Task Status →](15-task-status.md)
