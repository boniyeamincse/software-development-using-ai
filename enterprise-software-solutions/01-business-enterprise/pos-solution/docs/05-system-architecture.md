# 05 - POS System Architecture

## Hybrid Cloud-Edge Design
The POS Solution utilizes a **Distributed Edge Architecture** to ensure that physical registers remain functional and snappy even if the central cloud is unreachable.

## Technical Infrastructure
- **Frontend**: Next.js (React) for the web portal and a specialized Electron/Chromium wrapper for dedicated POS hardware.
- **Backend Edge**: Go or Rust-based local service running on store hardware to manage device drivers and offline sync.
- **Backend Cloud**: Node.js (TypeScript) or Java API for central data consolidation and reporting.
- **Messaging**: MQTT or WebSockets for real-time sales notifications between registers.

## Data Strategy
- **Local DB (SQLite/IndexedDB)**: Storing active catalog and last-24h transaction data for offline support.
- **Cloud DB (PostgreSQL)**: The master repository for all historical sales and global inventory data.
- **Hardware Bridge**: A specialized low-level layer to interface via USB, Bluetooth, or IP with printers and terminals.
