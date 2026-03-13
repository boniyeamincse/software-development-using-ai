# 11 - Restaurant Security & Resilience

## Financial Safety
- **PCI-DSS Compliance**: Using encrypted card readers (EMV) that isolate card data.
- **Tip Protection**: Detailed audit logs of tip adjustments to prevent staff theft.

## Operational Resilience
- **Offline Mode**: Automatic switching to "Local DB" if Wi-Fi or Internet fails.
- **Heartbeat Monitoring**: Pinging kitchen printers and KDS tablets every 60 seconds to detect failures.

## Privacy
- **Guest Data Anonymization**: Scrambling guest email/phone data used for marketing analytics (GDPR/CCPA).
- **RBAC**: Preventing servers from accessing the "Inventory Cost" or "Owner Financials" modules.

---
[← Previous: Technology Stack](10-tech-stack.md) | [Back to Index](README.md) | [Next: Deployment Strategy →](12-deployment.md)
