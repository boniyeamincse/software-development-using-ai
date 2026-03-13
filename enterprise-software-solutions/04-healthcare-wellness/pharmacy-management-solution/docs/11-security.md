# 11 - Pharmacy Security & Compliance

## Clinical Data Safety
- **HIPAA/GDPR Compliance**: Full encryption of patient medication history and PII.
- **Pharmacy Terminal Lockdown**: Terminals restricted to a "Whitelisted Browse" mode to prevent malware.
- **PHI Masking**: Insurance specialists see "Billing" data but clinical "Diagnoses" are masked unless authorized.

## Narcotics & Inventory Integrity
- **The "High-Alert" Lock**: Biometric fingerprint + Physical Key required for narcotics cabinet integration.
- **WORM Ledger (Write Once, Read Many)**: Ensuring narcotics logs cannot be edited or deleted once signed.
- **Video Audit Integration**: Mapping CCTV timestamps to narcotics dispensing events automatically.

## Infrastructure Resilience
- **Off-Grid Dispensing**: Ability to finish active fills using a local-cache database during an internet outage.
- **Redundant Insurance Links**: Multiple clearinghouse connections to prevent billing downtime.
- **Strict Role-Based Scoping**: Technicians can "Pack" but never "Final-Check" a clinical dispense.
