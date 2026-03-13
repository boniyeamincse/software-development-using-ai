# 09 - Patient Feedback System Workflows

## The Patient Feedback Journey
1. **Clinic Visit**: Patient finishes their appointment; EHR generates a "Checked-Out" event.
2. **Trigger**: System waits 2 hours (to allow for travel) and sends an SMS survey link.
3. **Submission**: Patient clicks the link, enters a 3-question survey in <30 seconds.
4. **Analysis**: NLP engine identifies the theme "Physician Manner" and sentiment "Very Positive."
5. **Morale Boost**: Comment is automatically shared to the Department Head's "Praise Feed."
6. **Retention**: Patient receives a brief "Thank You" message and is more likely to return.

## The Negative Recovery Workflow
1. Patient submits a score of 2/10 citing "Incorrect Billing Information."
2. System identifies the score and the "Billing" theme.
3. **Red-Alert**: Instant SMS/Push notification sent to the Billing Manager and Quality Lead.
4. **Resolution**: Billing Manager investigates, fixes the error, and calls the patient.
5. **Closure**: Manager records the outcome; System sends a brief "Was this resolved well?" survey.
6. **Learning**: Case details are used for the monthly "Quality Improvement" meeting.

## The Staff Recognition Workflow
1. Patient comment: "Nurse Sarah was amazing and calmed my nerves."
2. NLP identifies "Nurse Sarah" (Entity Recognition) and "Praise" (Sentiment).
3. System posts the quote to the Nurse Unit breakroom display.
4. Sarah receives a digital "Compassion Badge" on her employee profile.
5. Manager includes the patient praise in Sarah's annual performance review.
