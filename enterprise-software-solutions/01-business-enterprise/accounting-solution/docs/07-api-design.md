# 07 - Accounting API Design

## Ledger & Transactions
- `POST /api/v1/ledger/journal`: Create a balanced multi-line journal entry.
- `GET /api/v1/ledger/balance-sheet`: Fetch the current standing of all accounts.

## Billing & AR
- `POST /api/v1/billing/invoice`: Generate a new customer bill.
- `GET /api/v1/billing/aging`: Calculate AR aging report data.

## Banking
- `POST /api/v1/banking/reconcile`: Match bank statement lines to ledger transactions.
- `GET /api/v1/banking/feeds/sync`: Trigger a fetch of new transactions from connected banks.

## Security
- **Idempotency Headers**: Required for all transaction creation to prevent double-entries.
- **HMAC Signatures**: For all incoming calls from external payment or billing partners.
- **Mutual TLS**: Used for all communication with banking institutions.
