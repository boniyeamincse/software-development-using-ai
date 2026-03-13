# 09 - Library System Workflows

## Standard Circulation Cycle
1. **Search**: Student finds a book via OPAC; Sees location (Aisle/Shelf).
2. **Checkout**: Librarian (or Kiosk) scans barcode/RFID; System maps loan to student ID.
3. **Usage**: Student keeps book; System tracks the countdown to the due date.
4. **Reminder**: 2 days before due date, system sends an automated nudge.
5. **Return**: Book scanned at return desk; Loan marked "Complete"; Book status reverts to "Available."
6. **Maintenance**: If the book is flagged for "Restoration," status changes to "Inactive - Repair."

## Overdue & Fine Lifecycle
1. Due date passes without return; Loan status changes to "Overdue."
2. System daily increments a fine (e.g., $1.00/day).
3. Student's borrowing privileges are "Suspended" if fine exceeds $10.00.
4. On return, student prompted to pay fine via integrated portal.
