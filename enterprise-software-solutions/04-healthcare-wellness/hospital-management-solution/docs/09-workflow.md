# 09 - Hospital System Workflows

## The Emergency Admission Workflow
1. **Intake**: Trauma unit enters basic patient info or scans "John Doe" metadata.
2. **Prioritization**: Triage nurse assigns severity; Bed manager allocates "Red Zone" spot.
3. **Clinical Action**: Doctor enters "Stat" orders for Blood Gas and CT Scan via mobile app.
4. **Diagnostic Loop**: Lab receives automated alert; Samples processed; Results push immediately to EHR.
5. **Disposition**: Decision made for Surgery; OT Module reserves room; Blood bank verifies cross-match.
6. **Billing**: All trauma-meds and procedures are automatically added to the insurance ledger.

## The Medication Lifecycle
1. **Ordering**: Physician enters digital prescription; System checks for "Drug-Drug Interactions."
2. **Verification**: Clinical Pharmacist reviews and approves the order based on patient kidney function.
3. **Dispensing**: Pharmacy automation (Robot/Cabinet) picks the medication.
4. **Administration**: Nurse scans patient wristband and medication barcode; System verifies "The 5 Rights."
5. **Documentation**: Act is logged; Inventory decremented; Billing charged.

## The Discharge & Continuity Workflow
1. Physician enters "Discharge Order" after clinical milestones are met.
2. Pharmacy generates 7-day take-home supply.
3. Billing verifies insurance clearance and finalizes patient co-pay.
4. Discharge summary (PDF/FHIR) sent to the patient's primary care physician.
5. Bed status flips to "Cleaning Required" for housekeeping module.
6. Patient receives automated follow-up appointment invite via SMS.

---
[← Previous: UI Pages](08-ui-pages.md) | [Back to Index](README.md) | [Next: Technology Stack →](10-tech-stack.md)
