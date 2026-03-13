# Module: Enterprise Asset Management (EAM)

## Description
The **Enterprise Asset Management (EAM)** module manages the entire lifecycle of physical assets (machinery, vehicles, buildings, IT equipment) from acquisition through maintenance to final disposal.

## Business Purpose
Large organizations rely on high-value physical assets. This module maximizes "Return on Assets" (ROA) by reducing downtime through predictive maintenance and optimizing capital expenditure on new equipment.

## Key Features
* **Asset Lifecycle Registry**: Digital twin of every physical asset with serial numbers and warranty info.
* **Predictive Maintenance (PdM)**: Integration with IoT sensors to predict failures before they happen.
* **Work Order Orchestrator**: Scheduling and dispatching maintenance crews for repairs.
* **MRO (Maintenance, Repair, and Operations) Inventory**: Specialized inventory for spare parts and tools.
* **Depreciation & Valuation**: Automated financial tracking of asset value over time.

## User Roles
* **Asset Manager**: Oversees capital allocation and asset health strategy.
* **Maintenance Engineer**: Executes work orders and logs repair hours.
* **Finance Officer**: Tracks depreciation and insurance for high-value items.
* **Procurement Lead**: Manages MRO supplier relationships.

## Workflow
1. **Onboarding**: Asset is registered with its technical specifications and maintenance schedule.
2. **Monitoring**: IoT sensors stream data to the ERP (e.g., temperature/vibration).
3. **Alerting**: System detects a thermal anomaly and auto-creates a Work Order.
4. **Execution**: Maintenance Engineer receives the order on a mobile device and requests a spare part from MRO.
5. **Closure**: Repair is logged; asset health score is updated in the registry.

## Database Tables
* `assets_master`: Core registry of all physical items.
* `maintenance_schedules`: Calendar of planned service tasks.
* `work_orders`: Tracking of repair incidents and labor hours.
* `asset_depreciation_logs`: Financial history of asset value.

## API Endpoints
* `GET /api/v1/assets/health`: Summary of operational status across the fleet.
* `POST /api/v1/assets/work-orders`: raise a new repair request.
* `PUT /api/v1/assets/{id}/status`: Update asset from "Active" to "Maintenance" or "Decommissioned".
* `GET /api/v1/assets/valuation-report`: Financial report for accounting integration.

---
[← Previous: Quality Management](17-quality-management.md) | [Back to Index](README.md)
