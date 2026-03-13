# 11 - POS Security & Payment Safety

## Payment Integrity (PCI-DSS)
- **Point-to-Point Encryption (P2PE)**: Ensuring card data is never decrypted or stored on the POS hardware.
- **Tokenization**: Using single-use tokens for transaction processing instead of actual card numbers.

## Internal Fraud Prevention
- **Manager Overrides**: Requiring physical key-cards or biometric auth for voids and high-value discounts.
- **Cash Drawer Lockout**: POS logic prevents subsequent sales until the drawer is physically closed.
- **Blind Drops**: Managers must count cash without seeing the "Expected" system total to ensure honest reporting.

## Infrastructure Safety
- **Endpoint Lockdown**: Hardware restricted to a "Kiosk Mode" to prevent employees from browsing the web or installing external apps.
- **Network Isolation**: POS VLAN separating transactional traffic from store guest Wi-Fi.
- **Audit Logging**: Immutable history of every price change, void, and manual drawer opening.
