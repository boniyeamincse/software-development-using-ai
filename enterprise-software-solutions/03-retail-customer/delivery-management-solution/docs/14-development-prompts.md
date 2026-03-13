# 14 - Delivery Management Development Prompts

## Fleet & Route Optimization
### Prompt 1: Multi-Stop Route Optimization Algorithm
"Implement a route optimization algorithm (Solving the Traveling Salesperson Problem/VRP) in Python or Java. The algorithm must handle 50+ stops per vehicle, account for real-time traffic data, vehicle capacity constraints, and specific 'Delivery Windows' requested by customers. Optimize for both fuel efficiency and delivery speed."

### Prompt 2: Dynamic Fleet Dispatcher
"Design a real-time dispatching service that assigns new pickup requests to the closest available driver with sufficient capacity. Use a Geo-indexing library like Redis Geo or PostgreSQL PostGIS for efficient 'Radius Search' and 'Distance Calculation'."

## Real-Time Logistics
### Prompt 3: WebSocket-based Live Track-and-Trace
"Develop a real-time tracking architecture using WebSockets. Drivers should broadcast their GPS coordinates every 5 seconds, and the system should update the customer's map view with sub-second latency. Include logic to estimate 'Time of Arrival' (ETA) based on current speed and traffic."

### Prompt 4: Proof of Delivery (PoD) Service
"Create an API for capturing multi-modal Proof of Delivery. Support digital signatures, photo evidence (stored in S3), and GPS timestamping. ensure the PoD is instantly accessible to the sender via a secure URL once the delivery is marked 'Complete'."

## Driver Workspace & UX
### Prompt 5: Offline-First Driver Mobile App architecture
"Design the architecture for a driver mobile app using React Native and SQLite. Drivers must be able to view their route, scan barcodes, and capture signatures even in 'dead zones' with no internet. Implement a background sync worker that pushes all pending updates once a connection is restored."

### Prompt 6: Driver Performance & Safety Monitor
"Implement a service that analyzes driver behavior using accelerometer and GPS data (e.g., harsh braking, rapid acceleration, speeding). Generate a daily 'Safety Score' for each driver and provide actionable feedback in their companion app."

## trust & Security
### Prompt 7: Geofenced Arrival Notifications
"Develop a service that triggers an automated 'Driver is Nearby' notification (SMS/Push) when the vehicle enters a 500-meter radius of the delivery address. Include a 'Call Driver' button that uses a masked number service (like Twilio Proxy) to protect privacy."

### Prompt 8: Package Integrity & Audit Log
"Design an immutable audit log for package handling. Track every 'Hand-off' (Warehouse -> Sort Center -> Driver -> Customer) with unique device IDs and timestamps. This log should be the single source of truth for dispute resolution."

## Analytics & specialized Features
### Prompt 9: Delivery ROI & Cost-per-Mile Report
"Create a financial analytics tool that calculates 'Cost per Mile', 'Revenue per Route', and 'Driver Utilization'. Provide week-over-week comparisons to identify regions where logistics costs are exceeding targets."

### Prompt 10: AI Demand Forecasting for Fleet Scaling
"Develop a machine learning model that predicts future delivery volume based on historical trends and upcoming local events. Provide recommendations for temporary fleet scaling (e.g., hiring 20% more third-party couriers) for the upcoming weekend."
