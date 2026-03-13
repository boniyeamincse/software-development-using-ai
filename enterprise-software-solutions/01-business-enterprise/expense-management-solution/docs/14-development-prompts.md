# 14 - Expense Management Solution Development Prompts

## Capture & digitization
### Prompt 1: High-Fidelity OCR Receipt Scanner
"Design an architecture for a receipt digitization service. Use OCR (Optical Character Recognition) to extract 'Merchant Name', 'Date', 'Amount', and 'Currency' from uploaded images (JPG/PDF). Implement a 'Confidence Score' and flag records for manual review if the extraction is uncertain."

### Prompt 2: Mobile-First Receipt Capture & Sync
"Develop a mobile React Native module for instant receipt capture. Support 'Offline Mode' where photos are stored locally and automatically synced to the server when a connection is restored. Implement 'Auto-Cropping' and 'Image Enhancement' for better OCR results."

## Policy & Compliance
### Prompt 3: Dynamic Corporate Policy Engine
"Implement a rule-based engine that validates expenses against company policies. For example: 'Flag meals over $50', 'Require receipt for all items over $25', and 'Check for duplicate submissions by the same user'. Provide real-time feedback to the user during submission."

### Prompt 4: multi-Stage Approval State Machine
"Create a workflow for expense approvals. Support 'Manager' → 'Department Head' → 'Finance' tiers. Implement 'Auto-Approval' for expenses under $10 and 'Automatic Escalation' if a manager doesn't act within 48 hours."

## trust, Audit & Privacy
### Prompt 5: Immutable Expense Audit Transaction Vault
"Design a secure, write-once-read-many (WORM) audit log for all expense movements. Every submission, rejection reason, and payment status update must be hashed and stored to ensure a permanent, tamper-proof audit trail for tax compliance."

### Prompt 6: GDPR-Compliant Personal Data Handler
"Implement a secure workflow for managing employee banking and PII (Personally Identifiable Information). Ensure that sensitive data is encrypted at rest and masked in the UI for anyone except authorized finance personnel."

## Integration & Finance
### Prompt 7: Corporate Card Real-time Sync Hub
"Design an integration API that pulls real-time transaction data from corporate credit card providers (e.g., Visa, Mastercard, AMEX). Automatically match card transactions with scanned receipts and flag 'Missing Documentation'."

### Prompt 8: direct Reimbursement & Payroll Bridge
"Develop a service that triggers reimbursements directly via bank transfer or integrated payroll systems (like Wise or local banks). Support 'Batch Payment' generation and record the 'External Transaction ID' back in the expense ledger."

## Analytics & specialized Features
### Prompt 9: Executive Spending & ROI Dashboard
"Create a data visualization dashboard tracking 'Category Spending', 'Departmental Budgets', and 'Average Reimbursement Time'. Provide drill-down reports to identify high-spending merchants and policy violation trends."

### Prompt 10: AI-Powered Fraud Detection
"Develop a machine learning model that identifies 'Suspicious Patterns' in expense claims (e.g., claiming the same receipt multiple times, frequent 'Round Number' entries, or personal expenses tagged as business). Provide a 'Risk Score' for every claim."

---
[← Previous: Roadmap & Future Enhancements](13-future-features.md) | [Back to Index](README.md) | [Next: Task Status →](15-task-status.md)
