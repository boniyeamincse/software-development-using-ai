# 11 - Coupon Security & Abuse Prevention

## Integrity
- **Atomicity**: Using Redis LUA scripts to ensure "Increment Usage" and "Verify Budget" happen as a single atomic operation.
- **Signed Evaluation**: The E-commerce checkout MUST provide a signed token from the evaluation engine to finalize the order, preventing price tampering in the browser.

## Fraud Prevention
- **IP & User Fingerprinting**: Limiting redemptions based on browser fingerprints if Guest Checkout is enabled.
- **Pattern Matching**: Blocking sequential code attempts (brute force).

## Privacy
- **Audit Trails**: Recording WHO created/edited a discount and WHEN.
- **RBAC**: Ensuring only authorized personnel can generate bulk codes.

---
[← Previous: Technology Stack](10-tech-stack.md) | [Back to Index](README.md) | [Next: Deployment Strategy →](12-deployment.md)
