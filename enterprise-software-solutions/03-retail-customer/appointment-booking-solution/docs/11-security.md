# 11 - Appointment Booking Security

## Data Protection
- **Encryption**: TLS 1.3 for data in transit; AES-256 for student/client data at rest.
- **PII Stripping**: Automated logs masking for phone numbers and emails.

## Operational Integrity
- **Anti-Bot Logic**: CAPTCHA on the public booking portal to prevent spam bookings.
- **Rate-Limiting**: Throttling requests to the availability endpoint to prevent scraping.

## Compliance
- **PCI-DSS**: Ensuring card data never hits the internal server (Stripe Elements).
- **HIPAA (Optional)**: If used for medical appointments, stricter data access controls are activated.

---
[← Previous: Technology Stack](10-tech-stack.md) | [Back to Index](README.md) | [Next: Deployment Strategy →](12-deployment.md)
