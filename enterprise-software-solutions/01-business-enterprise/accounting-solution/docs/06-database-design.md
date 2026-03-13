# 06 - Accounting Database Design

## Core Schema Components

### 1. Chart of Accounts (COA)
- `account_id`, `account_code`, `name`, `type` (Asset/Liability/Equity/Income/Expense), `parent_id`

### 2. General Ledger (Double-Entry)
- `transaction_id`, `date`, `description`, `reference_no`
- `journal_entry_id`, `transaction_id`, `account_id`, `amount`, `type` (Debit/Credit)

### 3. Accounts Receivable (AR)
- `invoice_id`, `customer_id`, `issue_date`, `due_date`, `total_amount`, `status`
- `payment_id`, `invoice_id`, `amount_paid`, `date`, `method`

### 4. Accounts Payable (AP)
- `bill_id`, `vendor_id`, `received_date`, `due_date`, `amount_due`, `status`

### 5. Fixed Assets
- `asset_id`, `name`, `purchase_price`, `salvage_value`, `useful_life`, `depreciation_method`

## Key Relationships
- **One-to-Many**: One Transaction contains at least two Journal Entries (Total Debits = Total Credits).
- **One-to-Many**: One Customer has multiple Invoices.
- **Hierarchical**: The Chart of Accounts uses a recursive relationship for nested sub-accounts.
