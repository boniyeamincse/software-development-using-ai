# 09 - ERP System Workflows

## The "Procure-to-Pay" Lifecycle
1. **Demand**: Inventory falls below 10 units; System flags a shortage.
2. **Requisition**: Ops manager reviews and approves a new Purchase Requisition.
3. **Ordering**: System converts PR to a Purchase Order and emails the Vendor.
4. **Receipt**: Warehouse clerk scans arriving goods; Inventory increments instantly.
5. **Invoicing**: Finance receives vendor invoice; System matches it against the Receipt (3-Way Matching).
6. **Payment**: Accounts Payable executes payment; Ledger updated.

## The Production Workflow
1. **Order Ingest**: Sales order for 100 units of "Custom Product" is received.
2. **Component Check**: System verifies raw material availability via the BOM.
3. **Reservation**: Components marked as "Reserved"; Shortages triggered if necessary.
4. **Assembly**: Production order sent to manufacturing line; Daily progress logged.
5. **Finalization**: Finished goods move to "Sellable Inventory"; Manufacturing order closed.

---
[← Previous: UI Pages](08-ui-pages.md) | [Back to Index](README.md) | [Next: Technology Stack →](10-tech-stack.md)
