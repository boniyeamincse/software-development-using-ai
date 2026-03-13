# 14 - POS Solution Development Prompts

## Transaction & specialized Logic
### Prompt 1: High-Speed Transaction Core
"Design a PostgreSQL schema for a retail POS system. Support 'Split Payments' (Cash + Card), 'Promotion Logic' (buy-one-get-one, percentage off), and 'Offline Resilience'. Every transaction must generate a unique 'Fiscal Receipt ID' and be recorded in an immutable ledger."

### Prompt 2: Real-time Inventory & Stock Bridge
"Develop a service that automatically decrements stock levels across all locations in real-time as a sale is finalized. If stock falls below a 'Safety Level', trigger an automated 'Replenishment Request' to the central ERP system."

## Interaction & Hardware
### Prompt 3: Touch-Optimized Retail UI
"Create a React component for a retail checkout interface. Support 'Fast-Path' barcode scanning, 'Manual Search', and 'Quick-Action' buttons for common items. Ensure the UI is responsive and optimized for touch-screen input with large, clear hit-areas."

### Prompt 4: Omni-channel Hardware Hub
"Design an architecture for connecting POS hardware: Receipt Printers (ESC/POS), Barcode Scanners (USB/HID), and Credit Card Terminals (via API). Implement a 'Print Spooler' that handles offline printing and error recovery."

## Loyalty & Growth
### Prompt 5: Integrated Loyalty & Reward Engine
"Implement a service that calculates 'Loyalty Points' for every transaction. Support 'Tiered Rewards' (Silver, Gold, Platinum) and 'Point Redemption' at the point of sale. Provide a real-time 'Customer Insight' panel for the cashier showing previous purchases."

### Prompt 6: Gift Card & Store Credit Manager
"Develop a secure module for issuing and redeeming 'Digital Gift Cards' and 'Store Credits'. Support 'Partial Redemptions', 'Expiry Alerts', and 'Balance Inquiry' via QR code scanning at the POS terminal."

## Trust, Security & Audit
### Prompt 7: fiscal Compliance & Audit Vault
"Design a secure, write-once-read-many (WORM) audit log for all retail transactions. The system must comply with regional 'Fiscal Laws' ensuring that every sale is uniquely numbered and can be verified by tax authorities."

### Prompt 8: centralized Device Management & Security
"Implement a service that tracks the 'Health' and 'Security' of every POS terminal in the network. Support 'Remote Lockdown' for lost/stolen devices and 'Automated Updates' for security patches and price-books."

## Analytics & specialized Features
### Prompt 9: Real-time Store Performance Dashboard
"Create a data visualization dashboard tracking 'Daily Sales volume', 'Average Transaction Value' (ATV), and 'Top Performing Categories'. Provide 'Store-to-Store' comparison and 'Employee Sales Rankings'."

### Prompt 10: AI-Powered 'Next-Sell' Recommender
"Develop a recommendation engine that suggests 'Complementary Products' to the cashier during checkout based on the items currently in the cart (e.g., 'Would you like to add a Warranty?' or 'Customers also bought X')."

---
[← Previous: Roadmap & Future Enhancements](13-future-features.md) | [Back to Index](README.md) | [Next: Task Status →](15-task-status.md)
