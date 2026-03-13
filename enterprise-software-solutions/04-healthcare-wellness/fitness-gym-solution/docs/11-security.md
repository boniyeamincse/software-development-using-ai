# 11 - Fitness & Gym Security & Privacy

## Physical & Digital Safety
- **Anti-Passback Logic**: Preventing a single membership QR from being used for multiple entries in quick succession.
- **Dynamic QR Rotation**: Preventing "Screenshotted" codes from being shared with non-members.
- **CCTV Integration**: Mapping access-logs to video timestamps for security incident investigation.

## Data Privacy
- **Personal Info Masking**: Cleaning staff see member "Maintenance Request" names but not "Financial Information."
- **Audit Logs**: Comprehensive tracking of every staff interaction with member profiles.
- **Biometric Erasure**: If fingerprint/face-ID is used for entry, data is stored in localized, hashed-only formats.

## Infrastructure Integrity
- **Local Fallback**: Turnstiles continue to work using a local "Whitelist" during internet outages.
- **Secure Hardware Tunnels**: IoT gateways communicate over encrypted, VPN-protected links only.
- **PCI-DSS Compliance**: No raw credit card data is ever stored on gym servers.
