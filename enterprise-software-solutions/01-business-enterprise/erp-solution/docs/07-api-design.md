# 07 - ERP API Design

## Financial Transactions
- `POST /api/v1/finance/ledger`: create a new double-entry ledger record.
- `GET /api/v1/finance/balance`: Fetch real-time balance sheet snapshots.

## Inventory & Supply Chain
- `PATCH /api/v1/inventory/adjust`: Manually override stock counts during an audit.
- `GET /api/v1/supply-chain/shortages`: identify items below reorder thresholds.

## Manufacturing Coordination
- `POST /api/v1/manufacturing/order`: Trigger a new production run.
- `GET /api/v1/manufacturing/lines`: Status check of all assembly assets.

## Security
- **HMAC Signing**: For communication between remote warehouse terminals and the core API.
- **Mutual TLS (mTLS)**: For secure integration with external banking and regulatory APIs.
