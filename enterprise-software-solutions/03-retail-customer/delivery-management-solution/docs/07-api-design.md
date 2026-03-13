# 07 - Delivery API Design

## Dispatch & Status
- `POST /api/v1/dispatch/auto`: Trigger route optimization and order assignment.
- `PATCH /api/v1/shipment/:id/status`: Update status (e.g., "Picked Up").
- `GET /api/v1/tracking/:public_token`: Fetch live location for the customer.

## Driver Telemetry
- `POST /api/v1/telemetry/ping`: Ingest real-time GPS coordinates from driver app.
- `GET /api/v1/driver/manifest`: Fetch the sequenced list of stops for the driver.

## ePOD Integration
- `POST /api/v1/shipment/:id/proof`: Upload signature and photo evidence.

## Security
- **Dynamic Tokens**: Short-lived public tokens for customer tracking.
- **mTLS**: For secure communication between the Driver App and the Backend.
