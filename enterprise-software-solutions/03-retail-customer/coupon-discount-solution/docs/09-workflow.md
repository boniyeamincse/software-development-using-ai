# 09 - Coupon System Workflows

## The Promotion Lifecycle
1. **Design**: Marketing team creates a "Winter Sale" campaign with a 20% rule.
2. **Scheduling**: Campaign set to start at 12:00 AM on Dec 1st.
3. **Execution**: At checkout, the system automatically identifies applicable "Cart-Level" discounts.
4. **Validation**: User enters code "WINTER20"; System checks validity, customer eligibility, and budget.
5. **Calculation**: 20% is subtracted from the subtotal.
6. **Closing**: Order placed; Redemption record created; Budget counter incremented.

## Bundle Evaluation Workflow
1. Cart contains 2 T-shirts and 1 pair of Jeans.
2. Rule: "Buy 2 T-shirts, get Jeans 50% off."
3. Engine identifies the T-shirt pair -> flags the Jeans for discount.
4. If a 3rd T-shirt is added, the engine ignores it unless a "Stackable" rule applies.

---
[← Previous: UI Pages](08-ui-pages.md) | [Back to Index](README.md) | [Next: Technology Stack →](10-tech-stack.md)
