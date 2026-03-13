# 09 - POS System Workflows

## The Sales Lifecycle
1. **Identification**: Cashier scans customer loyalty QR or starts as "Guest."
2. **Scanning**: Items are scanned; System checks for "Promotions" and "Modifiers."
3. **Validation**: Price calculation with real-time tax based on location.
4. **Payment**: Terminal triggered; Encryption occurs at hardware level; Approval received.
5. **Fulfillment**: Inventory decremented in local cache; Receipt printed/emailed.
6. **Synchronization**: Transaction detail pushed to the cloud and central ERP.

## The Returns & Exchange Workflow
1. Customer provides digital or physical receipt.
2. System looks up transaction history and verifies "Return Window" (e.g., 30 days).
3. Items selected for return; Inventory incremented.
4. Refund triggered (original payment method or store credit).
5. New "Credit Note" generated and linked to the customer profile.

## The Offline Continuity Workflow
1. System detects internet loss.
2. UI remains active; Data written to local SQLite database.
3. Card processing shifts to "Store & Forward" (Offline Tokenization).
4. Internet restores; Background worker initiates "Reconciliation Handshake."
5. Sales merged into cloud master; Inventory audit check performed.

---
[← Previous: UI Pages](08-ui-pages.md) | [Back to Index](README.md) | [Next: Technology Stack →](10-tech-stack.md)
