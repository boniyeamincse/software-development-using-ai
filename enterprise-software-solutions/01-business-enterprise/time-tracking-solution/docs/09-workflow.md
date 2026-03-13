# 09 - Time Tracking System Workflows

## The Recurring Cycle (Entry to Payroll)
1. **Logging**: Employee starts timer on "Design Task A."
2. **Synchronization**: Active timer state synced to cloud every 60 seconds (Heartbeat).
3. **Closing**: User stops timer; Logs notes; Entry stored as "Draft."
4. **Draft Review**: At end of week, user reviews all drafts and clicks "Submit."
5. **Approval**: Project Manager reviews and Approves.
6. **Data Export**: System triggers sync to Accounting for customer billing and HRMS for payroll processing.

## Automated Overtime Calculation Workflow
1. User logs 10 hours in a single day.
2. System triggers Policy Check (e.g., "8 Hours Standard").
3. System automatically splits the entry into "8 Hours Regular" and "2 Hours Overtime (1.5x)."
4. Audit log created documenting the automatic policy application.

## Idle Time Recovery (Desktop)
1. Desktop client detects 10 minutes of no keyboard/mouse activity.
2. Timer paused; Notification appears: "You've been idle for 10 minutes."
3. User selects: "Keep Time," "Discard Time," or "Assign to Different Task."
4. Timer resumes based on user selection.

---
[← Previous: UI Pages](08-ui-pages.md) | [Back to Index](README.md) | [Next: Technology Stack →](10-tech-stack.md)
