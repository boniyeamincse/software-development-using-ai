# 11 - Hospital Security & Patient Privacy

## Medical Data Integrity (HIPAA/GDPR)
- **E2EE (End-to-End Encryption)**: Full encryption of Electronic Health Records (EHR) both in transit (TLS 1.3) and at rest (AES-256).
- **Break-the-Glass Protocol**: Allowing emergency access to patient records with mandatory, immediate high-level audit for unauthorized views.
- **PII De-identification**: Automated tool for cleaning patient data for research and analytics purposes.

## Clinical Safety & Device Security
- **Medical VLAN**: Isolating life-critical devices (ventilators, monitors) on a separate network from general hospital admin traffic.
- **Biometric Auth**: Mandatory fingerprint or facial recognition for accessing medicine cabinets and narcotics stores.
- **Immutable Audit Trails**: Non-destructive logging of every clinical decision, including who viewed which record and when.

## Resilience & Continuity
- **Trauma-Offline Mode**: ER registers can continue clinical documentation using local edge databases if the main cloud or data-center connectivity is lost.
- **Strict Identity Scoping**: Ensuring a Radiologist can see the "Lungs" but perhaps not the patient's "Psychiatric History" unless relevant.
- **Data Disposal Policies**: Automated enforcement of medical record retention laws (e.g., permanent deletion after 20 years).

---
[← Previous: Technology Stack](10-tech-stack.md) | [Back to Index](README.md) | [Next: Deployment Strategy →](12-deployment.md)
