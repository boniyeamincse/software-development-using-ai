# 09 - Telemedicine System Workflows

## The Virtual Care Journey
1. **Entry**: Patient clicks "Start Visit" from SMS/Email link.
2. **Pre-Flight**: Browser/Mobile app performs hardware check (Mic/Cam) and signs Consent.
3. **Queue**: Patient enters the Virtual Waiting Room; System notifies the provider.
4. **Consultation**: Provider joins; High-fidelity video session starts; Side-by-side charting.
5. **Prescribing**: Provider e-prescribes during the call; Patient verifies pharmacy on-screen.
6. **Closing**: Call ends; Feedback survey sent; Post-visit clinical summary pushed to Portal.

## The RPM Alert Workflow
1. Patient's home Oximeter detects SpO2 < 90%.
2. Device pushes data via mobile app to the RPM Hub.
3. System identifies anomaly; Triggers high-priority "Clinical Alert" for the Case Manager.
4. Nurse reviews trend; Initiates an "Urgent Virtual Visit" request to the patient.
5. Escalation is logged; Vital data is archived for the Physician's next review.

## The Async Messaging Workflow
1. Patient submits a photo of a rash via secure chat.
2. AI-Triage performs first-pass assessment; Routes to "Dermatology Queue."
3. Specialist reviews message during admin hours; Responds with clinical plan.
4. Patient notified; Views response and educational material in the portal.
5. Loop closed; Message archived in the medical record.

---
[← Previous: UI Pages](08-ui-pages.md) | [Back to Index](README.md) | [Next: Technology Stack →](10-tech-stack.md)
