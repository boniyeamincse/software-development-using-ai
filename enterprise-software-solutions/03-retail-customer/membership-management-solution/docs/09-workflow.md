# 09 - Membership Workflows

## The Onboarding Lifecycle
1. **Signup**: Member selects a plan on the website and pays the initiation fee.
2. **Setup**: Account created; Member asked to upload a profile photo for security.
3. **Activation**: Digital card issued; RFID tag linked (if applicable).
4. **Access**: Member scans at the gate; System authorizes entry.

## The Renewal & Dunning Lifecycle
1. **Trigger**: Subscription billing date reached.
2. **Execution**: System attempts to charge the card on file.
3. **Failure (if applies)**: Transaction fails; Status moves to "Past Due."
4. **Dunning**: automated "Payment Failed" emails sent every 2 days.
5. **Suspension**: After 7 days of failure, digital card is deactivated and gate access is denied.
6. **Recovery**: Member pays via portal; Access instantly restored.

## The Churn Prevention Flow
1. Automated tracker identifies a member hasn't scanned into the facility for 14 days.
2. System triggers a "We miss you" email with a small incentive (e.g., Free juice bar credit).

---
[← Previous: UI Pages](08-ui-pages.md) | [Back to Index](README.md) | [Next: Technology Stack →](10-tech-stack.md)
