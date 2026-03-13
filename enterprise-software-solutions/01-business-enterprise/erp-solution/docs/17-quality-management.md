# Module: Quality Management System (QMS)

## Description
The **Quality Management System (QMS)** module provides a centralized platform for managing product quality, regulatory compliance, and process improvements across the entire supply chain and manufacturing lifecycle. It ensures that every product reaching the customer meets predefined standards and safety regulations.

## Business Purpose
In an enterprise ERP, quality is not just a feature—it's a legal and competitive requirement. This module reduces waste (scrap/rework), ensures compliance with ISO standards, and protects the brand from recall-related liabilities.

## Key Features
* **Inspection Protocol Builder**: Define detailed testing steps for raw materials and finished goods.
* **Non-Conformance Reporting (NCR)**: Automated tracking of defects and deviations from standards.
* **CAPA (Corrective and Preventive Action)**: Workflow engine to identify root causes and prevent recurrence.
* **Audit Management**: Scheduling and executing internal/supplier quality audits.
* **Certificate of Analysis (CoA) Generator**: Automated document generation for shipments.

## User Roles
* **Quality Manager**: Oversees global quality strategy and CAPA approvals.
* **Quality Technician**: Conducts floor inspections and logs test results.
* **Production Supervisor**: Receives alerts on quality deviations.
* **Supplier Admin**: Responds to supplier corrective action requests (SCAR).

## Workflow
1. **Definition**: Quality Manager defines standards for a new Product SKU.
2. **Trigger**: System triggers an inspection task upon "Goods Receipt" in the Warehouse.
3. **Execution**: Technician performs tests and enters results into the system.
4. **Validation**: If results fail, a Non-Conformance Report (NCR) is auto-generated.
5. **Resolution**: CAPA process starts; material is quarantined until the Quality Manager releases it.

## Database Tables
* `quality_standards`: Master list of KPIs and acceptable ranges.
* `inspection_tasks`: Log of individual tests performed.
* `non_conformance_records`: Registry of quality failures.
* `capa_workflows`: Tracking of improvement initiatives.

## API Endpoints
* `GET /api/v1/quality/inspections`: Retrieve pending quality tasks.
* `POST /api/v1/quality/inspections`: Log a new test result.
* `PUT /api/v1/quality/ncr/{id}/status`: Update the status of a failure report.
* `GET /api/v1/quality/coa/{shipmentId}`: Generate a Certificate of Analysis.

---
[← Previous: Complete Modules List](16-complete-modules-list.md) | [Back to Index](README.md)
