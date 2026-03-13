# 09 - Medical Billing System Workflows

## The Revenue Cycle Workflow
1. **Clinical Close**: Provider finishes encounter; Data flows into Billing Solution.
2. **Scrubbing**: System automatically runs claim against 500+ payer-specific rules.
3. **Submission**: Clean claims are batched and sent (837) to the Clearinghouse.
4. **Adjudication**: Payer reviews claim; Sends back "Accepted" or "Denied" status.
5. **Payment**: Payer sends 835 ERA file; System auto-posts payments and adjustments.
6. **Secondary Billing**: If applicable, system triggers the secondary claim automatically.
7. **Patient Bill**: Final balance is calculated; Digital statement sent via SMS/Email.

## The Denial Management Workflow
1. Claim for "Item A" is denied due to "Missing Medical Necessity."
2. Billing Specialist is alerted via the "Priority Worklist."
3. Specialist reviews the clinical note and attaches the relevant PDF report.
4. "Appeal" is generated and resubmitted electronically with documents.
5. Status is tracked; Approval received; Payment posted.

## The Patient Collection Workflow
1. Initial statement sent; Patient views on their mobile device.
2. Patient clicks "Set up Payment Plan" (3 months).
3. System validates the credit card and schedules the first installment.
4. Monthly auto-charges occur; Receipt sent via Email.
5. Final payment received; Claim status moved to "Settled/Paid in Full."
