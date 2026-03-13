# 09 - Clinic System Workflows

## The Outpatient Journey
1. **Self-Booking**: Patient receives SMS invite; Books a slot via the mobile portal.
2. **Pre-Intake**: Patient fills out a digital intake/history form at home.
3. **Arrival**: Receptionist clicks "Arrived"; Medical Assistant is notified.
4. **Vitals**: Assistant records BP/Weight; Patient moved to "Consulting Room 2."
5. **Consultation**: Doctor reviews history, types SOAP note, and clicks "Send RX to CVS."
6. **Checkout**: Patient pays co-pay at the front desk; Receives follow-up date.
7. **Engagement**: 24 hours later, system sends "How was your visit?" survey.

## Telemedicine Pivot Workflow
1. Patient selects "Video Visit" during booking.
2. System generates a secure link and adds it to the calendar.
3. 5 mins before: Patient enters virtual waiting room; Doctor joins.
4. Charting happens side-by-side with the video stream.
5. Digital summary and e-prescription sent via the secure portal immediately after.

## Insurance Claim Workflow
1. Visit finishes; System suggests ICD-10 codes based on the SOAP note context.
2. Billing Specialist reviews and clicks "Submit."
3. Claim sent to Clearinghouse; Status tracked in real-time.
4. Approval received; Payment auto-reconciled against the patient's bill.
5. If denied, system flags "Correction Needed" with suggested fixes.
