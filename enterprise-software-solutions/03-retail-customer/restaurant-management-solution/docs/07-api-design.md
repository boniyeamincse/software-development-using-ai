# 07 - Restaurant API Design

## Order Lifecycle
- `POST /api/v1/order/create`: Send a table's order to the kitchen.
- `PATCH /api/v1/order/:id/bump`: Finalize a prep-task on the KDS.
- `POST /api/v1/payment/finalize`: Close the check and calculate tips.

## Inventory Operations
- `GET /api/v1/inventory/alerts`: Fetch items below reorder thresholds.
- `POST /api/v1/inventory/audit`: Log a physical count event.

## External Integrations
- `POST /api/hub/delivery-ingress`: Receive an order from UberEats or DoorDash.
- `GET /api/v1/menu/public`: Fetch a formatted JSON of the current menu for the website.

## Security
- **Pin-Based Auth**: For fast server switching on shared FOH terminals.
- **mTLS / API Keys**: For securing communication between on-premise hardware and the Cloud.
