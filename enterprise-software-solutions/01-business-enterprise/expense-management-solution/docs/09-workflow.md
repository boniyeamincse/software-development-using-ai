# 09 - Expense System Workflows

## The "Receipt-to-Bank" Lifecycle
1. **Capture**: Employee snaps a photo of a taxi receipt; AI extracts $25, Date, and "Uber."
2. **Drafting**: Item saved to the user's digital wallet; User assigns it to "Project X."
3. **Submission**: At the end of the trip, user selects 10 items and clicks "Submit Report."
4. **Validation**: System checks for duplicates and policy breaches (No alcohol on weekdays).
5. **Approval**: Report routes to Manager; Manager clicks "Approve" on their mobile app.
6. **Processing**: Finance Admin verifies receipts; triggers "ACH Transfer."
7. **Conclusion**: Employee notified of payment; Transaction synced to the Accounting ledger.

## Automated Card Matching Workflow
1. Corporate card swiped at a hotel.
2. System receives transaction data via Bank Webhook.
3. System sends push notification: "Please upload the receipt for your $150 transaction at Marriott."
4. User uploads receipt; AI confirms the amount matches the card swipe.
5. Item marked as "Verified" and automatically added to the next report.

## Audit & Discard Workflow
1. System identifies two identical receipts submitted by different users for the same lunch.
2. Reports automatically flagged as "Potential Duplicate."
3. Notification sent to Finance Auditor for manual review.
4. If fraud confirmed, users notified and incident logged in the Audit Trail.
