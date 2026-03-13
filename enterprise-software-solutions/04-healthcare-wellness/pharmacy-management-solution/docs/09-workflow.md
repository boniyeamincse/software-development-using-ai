# 09 - Pharmacy System Workflows

## The Prescription Filling Lifecycle
1. **Intake**: E-Prescription received via FHIR/Surescripts; System notifies the tech.
2. **First Check**: Pharmacist reviews clinical appropriateness and insurance eligibility.
3. **Selection**: Technician scans the stock bottle; System verifies SKU and Expiry.
4. **Processing**: Pill-counting machine integration (if available); Label printed with QR code.
5. **Final Clinical Check**: Pharmacist scans the final package and verifies patient identity.
6. **Counseling**: Pharmacist reviews specific medication warnings with the patient.
7. **Dispense**: Patient pays co-pay; System decrements inventory and archives the log.

## The Narcotics Audit Workflow
1. Pharmacy closes at 9:00 PM; Lead Pharmacist initiates "Manual Reconciliation."
2. System displays digital quantities for high-risk drugs.
3. Pharmacist enters physical counts; System identifies "Zero Discrepancy."
4. Digital signature collected and sent to the immutable Compliance Vault.
5. If discrepancy found, system automatically creates an "Incident Case" for the CMO.

## Automated Procurement Workflow
1. Stock for Item X drops below "Reorder Point" (calculated by AI trends).
2. System checks "Preferred Vendor" list and generates a Draft RFP.
3. Inventory Manager reviews and clicks "Approve."
4. PO sent to Vendor; Tracking number ingested via API.
5. Shipment arrives; Barcode scan auto-populates batch data and stock quantity.

---
[← Previous: UI Pages](08-ui-pages.md) | [Back to Index](README.md) | [Next: Technology Stack →](10-tech-stack.md)
