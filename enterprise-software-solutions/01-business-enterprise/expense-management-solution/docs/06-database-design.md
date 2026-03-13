# 06 - Expense Database Design

## Core Schema Components

### 1. Expense Reports
- `report_id`, `user_id`, `title`, `status` (Draft/Submitted/Pending/Approved/Reimbursed), `total_amount`, `currency`

### 2. Expense Line Items
- `item_id`, `report_id`, `category_id`, `amount`, `tax_amount`, `date`, `vendor_name`, `receipt_url`

### 3. Spend Categories & Policies
- `category_id`, `name`, `gl_code` (for Accounting sync), `limit_amount`, `is_receipt_mandatory`

### 4. Reimbursement Logs
- `reimbursement_id`, `report_id`, `payment_method`, `date_paid`, `bank_ref_no`

### 5. Card Transactions
- `transaction_id`, `card_id`, `external_ref`, `amount`, `status` (Pending/Matched/Disputed)

## Key Relationships
- **One-to-Many**: One Expense Report contains multiple Line Items.
- **Many-to-One**: Many Line Items can refer to one Spend Category.
- **One-to-One**: One approved Expense Report results in one Reimbursement event.
