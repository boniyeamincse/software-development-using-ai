# 05 - ERP System Architecture

## Distributed & Modular Design
The ERP is built on a **Service-Oriented Architecture (SOA)**, allowing individual modules (Finance, Inventory, Manufacturing) to scale independently while sharing a common data model.

## Technical Infrastructure
- **Frontend**: React-Next.js for the administrative and operational web interfaces.
- **Backend API**: Java (Spring Boot) or C# (.NET Core) for enterprise-grade stability and strong typing.
- **Message Broker**: Apache Kafka or RabbitMQ for handling asynchronous inter-modular communications (e.g., "Order Paid -> Incur Inventory Deduction").
- **Reporting Engine**: Dedicated read-optimized service for complex financial aggregations.

## Data Layer
- **Primary Database (PostgreSQL)**: Storing the transactional "Source of Truth" with strict ACID compliance.
- **Data Warehouse (Snowflake)**: For long-term historical analysis and business intelligence.
- **Object Storage (S3)**: Storing invoices, legal documents, and large binary media.
