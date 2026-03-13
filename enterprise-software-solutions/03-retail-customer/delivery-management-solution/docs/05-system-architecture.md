# 05 - Delivery System Architecture

## Real-Time & Event-Driven Logic
The system is built on a **High-Throughput Geo-Spatial Architecture** to handle thousands of concurrent GPS pings and status updates.

## Technical Infrastructure
- **Frontend**: React (Control Center) and Native/Flutter (Driver App).
- **Backend API**: Go (Golang) for high-concurrency GPS ingestion and status updates.
- **Geo-Spatial Data**: PostGIS (PostgreSQL extension) for efficient location-based querying.
- **Messaging (Pub/Sub)**: Redis or MQTT for real-time location streaming to the customer portal.

## Performance Tier
- **Optimization Engine**: C++ or Rust based microservice for solving the Vehicle Routing Problem (VRP).
- **Cache**: Redis for storing current "Last Known Position" of all drivers.

---
[← Previous: User Roles & Permissions](04-user-roles.md) | [Back to Index](README.md) | [Next: Database Design →](06-database-design.md)
