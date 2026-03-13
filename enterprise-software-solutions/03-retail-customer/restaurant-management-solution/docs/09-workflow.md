# 09 - Restaurant System Workflows

## The Dine-In Order Lifecycle
1. **Seating**: Receptionist assigns guest to "Table 14" in the POS.
2. **Order**: Server takes order on a tablet; Modifier rules enforced.
3. **Routing**: System splits order: Drinks to Bar Printer; Steaks to Grill KDS.
4. **Kitchen Prep**: Chef selects "Start" on KDS; Timer begins.
5. **Execution**: Chef selects "Complete"; Expeditor notified to run the food.
6. **Billing**: Server prints check; Guest pays via credit card; Order marked "Paid."
7. **Cleanup**: Guest leaves; Table marked "Dirty" then "Available."

## Inventory Depletion Workflow
1. Item "Classic Burger" marked "Closed/Paid" at POS.
2. System looks up linked recipe: 200g Beef, 1 Bun, 20g Sauce.
3. Theoretical inventory decremented in the DB for those 3 SKUs.
4. If Beef falls below 5kg, an automated "Low Stock Alert" sent to Manager.

---
[← Previous: UI Pages](08-ui-pages.md) | [Back to Index](README.md) | [Next: Technology Stack →](10-tech-stack.md)
