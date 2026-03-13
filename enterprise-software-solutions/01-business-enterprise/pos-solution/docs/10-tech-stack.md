# 10 - POS Technology Stack

## Frontend & Edge
- **Web App**: Next.js (React).
- **Desktop Wrapper**: Electron with native node-modules for device driver access.
- **Local DB**: SQLite or IndexedDB.

## Backend & Logic
- **Cloud API**: Node.js (TypeScript) or Go.
- **Master Database**: PostgreSQL (Cloud) with TimescaleDB for sales analytics.
- **Real-Time**: MQTT (for store notifications) and WebSockets.

## Hardware Integration
- **Drivers**: ESC/POS for printers, HID for barcode scanners, OPOS/JavaPOS for complex peripherals.
- **Payments**: Integration with Stripe Terminal, Adyen, or Square SDKs.

## Infrastructure
- **Deployment**: Multi-region AWS for the cloud; Edge-computing for local store servers.
- **Monitoring**: Datadog (Cloud) + Local health checks for physical hardware.
