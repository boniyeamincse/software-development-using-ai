# 06 - Delivery Database Design

## Core Schema Components

### 1. Shipments & Packages
- `shipment_id`, `order_ref`, `customer_id`, `recipient_name`, `address_point` (GEOMETRY), `status` (Unassigned/In-Transit/Delivered)

### 2. Fleet & Drivers
- `driver_id`, `vehicle_id`, `current_lat`, `current_lng`, `status` (Online/Busy/Offline)

### 3. Routes & Tasks
- `route_id`, `driver_id`, `planned_path` (LINESTRING), `scheduled_start`, `scheduled_end`
- `task_id`, `route_id`, `shipment_id`, `sequence_number`, `eta`

### 4. Proof of Delivery (ePOD)
- `epod_id`, `shipment_id`, `signature_url`, `photo_url`, `timestamp`, `delivery_location` (GEOMETRY)

## Key Relationships
- **One-to-Many**: One Driver can have multiple Routes (over time).
- **One-to-Many**: One Route contains multiple Tasks/Stops.
- **One-to-One**: One Shipment has one ePOD record.

---
[← Previous: System Architecture](05-system-architecture.md) | [Back to Index](README.md) | [Next: API Design →](07-api-design.md)
