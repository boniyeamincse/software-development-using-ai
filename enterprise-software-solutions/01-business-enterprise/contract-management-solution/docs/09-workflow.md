# 09 - Contract System Workflows

## The "Request-to-Renewal" Lifecycle
1. **Request**: Sales team clicks "New Contract" and selects the "standard MSA" template.
2. **Drafting**: System auto-populates party names from the CRM; Legal reviews the first draft.
3. **Negotiation**: Counter-party receives invitation; Redlines are exchanged and resolved in-platform.
4. **Approval**: Final draft routes to the CFO for business approval.
5. **Execution**: System sends to DocuSign; Parties sign; Final PDF is automatically archived.
6. **Activation**: Dates are pushed to the Milestone Engine; Alerts set for 11 months from now.
7. **Renewal**: System notifies Legal: "Contract with Client X expires in 30 days. Renew?"

## AI Document Extraction Workflow
1. New PDF is uploaded to the repository.
2. OCR converts image to text; NLP models analyze for entities.
3. System suggests metadata: "Effective Date: Jan 1, 2026," "Value: $500,000."
4. Human user clicks "Verify" to lock the data into the relational database.

## Redline Conflict Workflow
1. User A (Internal) and User B (External) edit the same clause simultaneously.
2. System identifies the overlap and enters "Conflict Mode."
3. Both users see a side-by-side comparison of the two versions.
4. Lead negotiator selects the winning text or drafts a new compromise.
5. History log notes the resolution detail for future audit.

---
[← Previous: UI Pages](08-ui-pages.md) | [Back to Index](README.md) | [Next: Technology Stack →](10-tech-stack.md)
