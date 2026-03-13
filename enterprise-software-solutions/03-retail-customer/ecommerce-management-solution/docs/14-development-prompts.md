# 14 - Ecommerce Management Development Prompts

## Core Storefront & Catalog
### Prompt 1: High-Performance Product Indexing
"Design a PostgreSQL schema and ElasticSearch mapping for a catalog of 1 million+ products. Include support for complex attributes (size, color, material), multi-level categories, and real-time inventory updates. Implement a 'Search-as-you-type' feature with typo tolerance using Edge N-grams."

### Prompt 2: Dynamic Pricing & Flash Sale Engine
"Implement a Node.js service for a dynamic pricing engine. The service should handle 'Flash Sales' with millisecond accuracy, manage 'Buy X Get Y' promotions, and support price overrides based on user loyalty levels and geographic location."

## Shopping Experience & Checkout
### Prompt 3: Distributed Cart Service with Redis
"Develop a high-availability shopping cart service using Redis. The service must handle millions of concurrent sessions, support 'Guest-to-User' cart merging upon login, and implement an 'Abandoned Cart' trigger that sends a notification after 2 hours of inactivity."

### Prompt 4: multi-currency Checkout Orchestration
"Write a backend service to orchestrate a global checkout flow. Integrate with Stripe and PayPal for payments, and Avalara or TaxJar for real-time tax calculation. Handle currency conversion at the current market rate and provide an itemized breakdown of landed costs (DPR/DDP)."

## Logistics & Fulfillment
### Prompt 5: Order Management System (OMS) State Machine
"Implement a robust Order State Machine (Pending, Paid, Processing, Shipped, Delivered, Returned). Every state transition must be recorded in an immutable audit log. Include hooks for triggering 'Low Stock' alerts when an order is moved to 'Processing'."

### Prompt 6: Intelligent Shipping Carrier Selector
"Develop an algorithm that selects the optimal shipping carrier (UPS, FedEx, DHL) based on package weight, dimensions, destination, and the customer's selected delivery speed. Integrate with carrier APIs to generate shipping labels and tracking numbers automatically."

## Security & trust
### Prompt 7: PCI-DSS Compliant Payment Tokenization
"Design the architecture for a secure payment tokenization system. Ensure that no raw credit card data ever touches the application server. Explain how you would use iFrame-based field injection (like Stripe Elements) to minimize PCI-DSS audit scope."

### Prompt 8: AI-Driven Fraud Detection Filter
"Build a preliminary fraud detection layer that analyzes order metadata (IP geolocation, email age, billing/shipping mismatch). If the 'Risk Score' exceeds a threshold, move the order to a 'Manual Review' state and notify the risk management team."

## Analytics & specialized Features
### Prompt 9: Real-time Sales Performance Dashboard
"Create a data visualization service that tracks 'Converson Rate', 'Average Order Value' (AOV), and 'Customer Acquisition Cost' (CAC) in real-time. Output the data in a format suitable for Recharts or Chart.js implementation."

### Prompt 10: Product Recommendation Engine (RAG-based)
"Develop a recommendation service that uses vector search (e.g., Pinecone or pgvector) to suggest products based on a user's browsing history and past purchases. Implement 'Complete the Look' logic for fashion-based ecommerce."
