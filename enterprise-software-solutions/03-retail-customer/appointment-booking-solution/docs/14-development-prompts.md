# 14 - Appointment Booking Development Prompts

## Scheduling Logic
### Prompt 1: High-Concurrency Availability Engine
"Design a PostgreSQL schema and a Node.js service for a high-concurrency availability engine. The system must support diverse booking types (Individual, Group, Resource-based) and handle 'Buffer Times' before and after each appointment. Implement a search for 'Next Available Slot' across multiple providers in a specific geographic area."

### Prompt 2: Dynamic Calendar Sync Algorithm
"Implement an algorithm that syncs external calendars (Google, Outlook, iCal) in real-time. The system must detect conflicts in the external calendar and automatically mark those times as 'Busy' in the local database. Handle time zone conversions and DST changes gracefully."

## User Engagement & Conversion
### Prompt 3: Multi-Stage Booking Workflow
"Develop a React-based multi-stage booking widget. Stages: 1. Service Selection, 2. Provider/Location Selection, 3. Date/Time Picker, 4. Customer Info & Intake Form, 5. Payment & Confirmation. Use a state management library (like Redux or Zustand) to maintain data across steps and support 'Back' navigation."

### Prompt 4: Proactive Waitlist Management
"Create a backend service for 'Proactive Waitlists'. If a high-demand slot becomes available due to a cancellation, the service should automatically notify the first 5 people on the waitlist via Push/SMS. Implement a 'First-to-Claim' logic with a 15-minute expiration."

## Operation & specialized Features
### Prompt 5: Automated Intake Form Builder
"Design a tool for admins to build custom 'Intake Forms' for different service types. Support conditional fields (e.g., 'If first-time client, show Medical History section'). Form data should be versioned and stored securely in a JSONB format."

### Prompt 6: Service-Specific Resource Allocator
"Develop a logic that automatically links specific resources (Rooms, Equipment) to an appointment. For example, a 'Laser Hair Removal' appointment must automatically block a specific 'Laser Machine' and a 'Treatment Room'. Prevent bookings if the required resource is unavailable."

## Trust & Reliability
### Prompt 7: SMS/Email Reminder Orchestrator
"Implement a notification service that sends multi-stage reminders: 1. Instant Confirmation, 2. 24-hour Reminder, 3. 1-hour 'Heading there?' alert. Support two-way SMS where a customer can reply 'CANCEL' or 'RESCHEDULE' to trigger automated workflows."

### Prompt 8: Secure Deposit & No-Show Protection
"Integrate Stripe to handle 'Deposit-only' bookings and 'No-show Protection' (where a card is held but only charged if the customer fails to appear). Implement logic for 'Cancellation Windows' where the deposit is only refundable if cancelled X hours in advance."

## Intelligence & Analytics
### Prompt 9: Provider Performance & Utilization Report
"Create a data analytics service that calculates 'Provider Utilization' (Actual booked time vs. available time) and 'No-show Rates'. provide visualization-ready data for an admin dashboard to optimize staffing levels."

### Prompt 10: AI-Powered Schedule Optimizer
"Develop a service that suggests 'Optimal Shift Patterns' for providers based on historical booking density. Identify 'Peak Times' and recommend bridge shifts to maximize ROI during high-demand periods."
