# 09 - Accounting System Workflows

## The "Record-to-Report" Lifecycle
1. **Entry**: A transaction occurs (Sales Order, Expense, Bank Fee).
2. **Validation**: System ensures equal Debits/Credits and valid Account codes.
3. **Posting**: Transaction is committed to the immutable General Ledger.
4. **Reconciliation**: Bank statement is matched against the Ledger to ensure 1:1 accuracy.
5. **Closing**: Month-end adjustments made (Depreciation, Accruals); Period is locked.
6. **Reporting**: Final financial statements are generated for stakeholders.

## Automated Bank Reconciliation Workflow
1. System fetches daily feed from the connected Bank.
2. AI Engine compares amounts and dates to existing "Draft" entries.
3. High-Confidence matches are pre-selected for the Accountant.
4. Low-Confidence items are flagged for manual categorization.
5. Once "Bank Balance" equals "Book Balance," the reconciliation is closed.

## Multi-Currency Transaction Workflow
1. Transaction entered in EUR ($1,000).
2. System fetches real-time spot rate from Integrated Forex Provider.
3. Ledger tracks both "Transaction Currency" (EUR) and "Base Currency" (USD).
4. At period-end, system calculates Unrealized Gain/Loss based on current rates.
