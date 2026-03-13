# 14 - Restaurant Management Development Prompts

## Reservation & Floor Management
### Prompt 1: High-Concurrency Table Reservation Logic
"Design a PostgreSQL schema for a restaurant reservation system. The schema must handle different table sizes, overlapping reservation 'Turns' (e.g., 2-hour slots), and 'Table Joining' for large groups. Implement a search for 'Available Tables' that optimizes for seating capacity utilization."

### Prompt 2: Real-time Interactive Floor Plan
"Develop a React-based floor plan editor and viewer. Admins should be able to drag-and-drop tables, define 'Sections' (Indoor, Patio, Bar), and see real-time status of each table (Available, Seated, Dirty). use HTML5 Canvas or SVG for the rendering layer."

## Order & Kitchen Operations
### Prompt 3: Kitchen Display System (KDS) Queue
"Implement a real-time KDS using WebSockets. Orders from the POS (Point of Sale) should appear instantly, grouped by 'Course' (Appetizers, Mains, Desserts). Include 'Fire' logic where a server can signal the kitchen to start the next course, and track 'Preparation Time' for every dish."

### Prompt 4: Dynamic Menu & Inventory Depletion
"Create a backend service that manages a dynamic menu. Support '86-ing' items (marking as unavailable) in real-time. Link menu items to a 'Recipe Ingredient' list so that every sale automatically depletes stock in the Inventory module."

## Guest Experience & Checkout
### Prompt 5: Contactless QR Code Ordering Architecture
"Design the architecture for a QR-code based ordering system. include support for 'Open Tabs' (Pay-at-end) and 'Instant Pay'. Handle table-specific ID injection in the URL to ensure orders are routed to the correct physical location."

### Prompt 6: Split-Check & Gratuity Calculator
"Develop a logic for 'Complex Bill Splitting' (Split by Item, Split Evenly, or Custom amounts). Integrate with a payment gateway to handle multiple partial payments for a single order and automatically calculate recommended gratuity percentages."

## Staff & Operations
### Prompt 7: Waitlist & Pager Notification Hub
"Build a module to manage 'Walk-in' waitlists. capture customer phone numbers and send an automated SMS notification when their table is ready. Implement a 'Wait Time Prediction' algorithm based on current table turnover rates."

### Prompt 8: Employee Shift & Tip Pooling Tracker
"Create a service for managing staff shifts and 'Tip Pooling'. Support different pool types (e.g., 70% to Front-of-House, 30% to Back-of-House) and generate a daily 'Payout Report' for employees."

## Analytics & specialized Features
### Prompt 9: Menu Engineering & Profitability Report
"Create a data analytics tool that categorizes menu items into 'Stars' (High profit, High volume), 'Plowhorses' (Low profit, High volume), 'Puzzles' (High profit, Low volume), and 'Dogs' (Low profit, Low volume) using the menu engineering matrix."

### Prompt 10: AI Inventory Waste Predictor
"Develop a service that analyzes historical sales and weather data to predict daily ingredient needs. Provide 'Ordering Recommendations' to minimize food waste while ensuring high-demand items never run out."

---
[← Previous: Roadmap & Future Enhancements](13-future-features.md) | [Back to Index](README.md) | [Next: Task Status →](15-task-status.md)
