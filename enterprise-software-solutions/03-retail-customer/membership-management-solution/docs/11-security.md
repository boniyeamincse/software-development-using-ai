# 11 - Membership Security & Access Integrity

## Data Safety
- **PCI Compliance**: Ensuring payment data is handled solely through encrypted tokenization (e.g., Stripe hosted fields).
- **SSO for Staff**: Integration with Okta or Google Workspace for secure admin access.

## Physical Integrity
- **Anti-Passback**: Logic that prevents a membership card from being used twice in a row at an entry gate without an exit event.
- **Photo Verification**: Displaying the member's photo on the staff monitor during every scan.

## Privacy
- **GDPR**: Tools for members to download their billing and attendance history.
- **Encryption**: sensitive info like addresses and agreement PDFs are encrypted at rest.
