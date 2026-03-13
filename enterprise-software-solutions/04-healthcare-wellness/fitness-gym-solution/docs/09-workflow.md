# 09 - Fitness & Gym System Workflows

## The Member Entry Journey
1. **Approach**: Member arrives at the gym and opens the app.
2. **Identification**: Member scans the dynamic QR code at the turnstile.
3. **Validation**: Edge-controller checks local cache for "Active Status" and "Unpaid Balance."
4. **Action**: Turnstile unlocks; System records "Check-in" timestamp.
5. **Notification**: Staff dashboard shows the member's photo and welcome message.
6. **Engagement**: 60 mins later, system sends "How was your workout?" push notification.

## The Class Booking Workflow
1. Member views "Evening Yoga" on the app; Sees "Waitlist Only."
2. Member joins the Waitlist.
3. Another member cancels their spot 2 hours before the class.
4. System automatically promotes the first waitlisted member and sends an SMS alert.
5. Member clicks "Confirm"; Spot is locked.
6. Instructor views the final roster and marks attendance during start-time.

## The Membership Churn Prevention Workflow
1. System identifies Member X has not checked in for 14 consecutive days (The "Ghost" Flag).
2. Automated SMS sent: "We miss you! Here is a free smoothie code for your next visit."
3. 21 days: Personal Trainer notified to send a 1-on-1 motivational message.
4. 30 days: System flags for "Retention Call" by the Front Desk manager.
5. Successful outcome: Member checks in; "Ghost" flag cleared; Loyalty points awarded.
