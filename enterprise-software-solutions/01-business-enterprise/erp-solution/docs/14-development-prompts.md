# 14 - ERP Solution Development Prompts

## Resource & Inventory Orchestration
### Prompt 1: Multi-Warehouse Inventory Controller
"Design a PostgreSQL schema for a global inventory system. Support multiple warehouses, 'Soft-Allocations' (items in cart/order but not shipped), and 'Batch/Serial Number' tracking. Implement a 'Reorder Trigger' service that alerts procurement when stock levels hit a safety threshold."

### Prompt 2: Real-time Production Line Scheduler
"Develop a scheduling service for a manufacturing production line. The system must account for 'Machine Availability', 'Labor Capability', and 'Material Lead Times'. Implement an 'Alert System' for production delays due to equipment maintenance or material shortages."

## Finance & procurement
### Prompt 3: multi-Entity Consolidation Engine
"Create a financial consolidation service for companies with multiple legal entities. Support real-time currency conversion, inter-company transaction eliminations, and automated generation of a 'Universal Balance Sheet'."

### Prompt 4: Strategic Procurement & Vendor Scoring
"Implement a vendor management system that tracks 'Lead Time Accuracy', 'Price Variance', and 'Quality Defect Rate'. Use a weighted scoring algorithm to recommend the best vendor for a specific RFQ (Request for Quote)."

## Human Capital & Workflows
### Prompt 5: Global Payroll & Tax Orchestrator
"Design an architecture for a global payroll system. Support diverse pay cycles, regional tax rules (including deductions and benefits), and automated direct deposit file generation (ACH/SEPA). Implement a secure 'Employee Paystub Portal'."

### Prompt 6: workflow Automation for CapEx Approval
"Develop a state-machine based workflow for Capital Expenditure (CapEx) approvals. The workflow should route requests based on department, amount, and project priority. Every approval or rejection must be logged in an immutable audit trail."

## trust & Compliance
### Prompt 7: Immutable Audit Vault for SOX Compliance
"Design a secure, write-once-read-many (WORM) audit log for all financial and inventory movements. Ensure compliance with SOX (Sarbanes-Oxley) requirements for data integrity and traceability."

### Prompt 8: Enterprise-Grade RBAC & Row-Level Security
"Implement a complex RBAC system using PostgreSQL Row-Level Security (RLS). Ensure that regional managers can only see records for their specific region, while executive users maintain a global view across all departments."

## Analytics & specialized Features
### Prompt 9: Executive BI Dashboard (Real-time ROI)
"Create a data visualization dashboard tracking 'Net Profit Margin', 'Inventory Turnover', and 'Return on Assets' (ROA). Provide drill-down reports for departmental budget vs. actual spending."

### Prompt 10: AI-Powered Predictive Maintenance
"Develop a service that analyzes sensor data from industrial machinery using an IoT bridge. Predict 'Time-to-Failure' and automatically generate maintenance work orders before an actual breakdown occurs."

---
[← Previous: Roadmap & Future Enhancements](13-future-features.md) | [Back to Index](README.md) | [Next: Task Status →](15-task-status.md)
