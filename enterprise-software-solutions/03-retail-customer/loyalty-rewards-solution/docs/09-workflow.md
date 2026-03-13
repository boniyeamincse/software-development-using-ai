# 09 - Loyalty System Workflows

## The Earning Lifecycle
1. **Purchase**: Customer buys an item at the POS or Online.
2. **Identification**: System identifies the customer via email, phone, or loyalty card.
3. **Calculation**: The Rule Engine evaluates active multipliers (e.g., Birthday bonus).
4. **Ledgering**: Points are added to the DB in a transactional state.
5. **Notification**: Push notification sent: "You just earned 150 points!"

## The Redemption Lifecycle
1. **Selection**: Customer selects a 10% off voucher in the app.
2. **Verification**: System checks balance and voucher availability.
3. **Deduction**: Points are subtracted from the ledger; Status marked "Reserved."
4. **Issuance**: A unique discount code is generated and added to the customer's digital wallet.
5. **Finalization**: Code is used at checkout; Redemption status marked "Fulfilled."

## Tier Progression Workflow
1. Monthly CRON job evaluates total spend or point count for each member.
2. If criteria for next tier is met, member record is updated.
3. "Welcome to Gold Tier" sequence triggered (Email, Physical card, Bonus points).

---
[← Previous: UI Pages](08-ui-pages.md) | [Back to Index](README.md) | [Next: Technology Stack →](10-tech-stack.md)
