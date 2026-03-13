# 05 - Fitness & Gym System Architecture

## Hybrid Cloud & Hardware Edge Design
The Fitness Solution utilizes a **High-Availability Cloud Engine** paired with **Local Edge Controllers** to ensure gym access remains functional even during internet outages.

## Technical Infrastructure
- **Mobile Frontend**: React Native for a high-performance, cross-platform member experience.
- **Web Frontend**: Next.js (React) for administrative and staff control panels.
- **Backend API**: Node.js (TypeScript) or Go for high-concurrency booking and check-in logic.
- **IoT Hardware Bridge**: Local gateway (e.g., Raspberry Pi or specialized PLC) for turnstile control.

## Data & Access Strategy
- **Relational DB (PostgreSQL)**: Master data for members, contracts, and financial records.
- **Cache Layer (Redis)**: Real-time class availability and session state for the member app.
- **Edge Cache**: Localized copy of active member IDs at the physical gym location for offline entry.
- **Stream Processing**: Apache Kafka or RabbitMQ for processing high-volume check-in events and alerts.
