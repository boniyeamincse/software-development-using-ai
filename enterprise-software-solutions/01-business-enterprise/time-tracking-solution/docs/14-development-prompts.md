# 14 - Time Tracking Solution Development Prompts

## Capture & Precision
### Prompt 1: Omni-channel Time Capture Service
"Design an architecture for a global time tracking service. Support multiple capture methods: 'Manual Entry', 'Direct Start/Stop Timer', and 'Mobile GPS Check-in'. Implement a 'Conflict Resolver' logic that flags overlapping time entries for the same user."

### Prompt 2: cross-Platform Idle Detection Hub
"Develop a background service (for Desktop/Web) that detects user inactivity. If a timer is running and the user is idle for more than 5 minutes, automatically pause the timer and prompt the user to 'Keep', 'Discard', or 'Adjust' the idle time upon return."

## Approval & workflow
### Prompt 3: multi-Stage Timesheet Approval Engine
"Create a state-machine based workflow for timesheet approvals. Support 'Team Lead' → 'Department Head' → 'Finance' approval tiers. Implement automated 'Missing Timesheet' reminders for users who haven't submitted their hours by Friday evening."

### Prompt 4: Dynamic Billing & Budget Cap Alerts
"Implement a service that links tracked time to fixed-price or hourly projects. Automatically trigger an 'Alert' (via Email/WebHook) when a project's billable hours reach 80% and 100% of the allocated budget."

## Trust, Integrity & compliance
### Prompt 5: Immutable Time-Audit Transaction Vault
"Design a secure, write-once-read-many (WORM) audit log for all time entries. Every addition, deletion, or manual adjustment to a time record must be hashed and stored with the original rationale for the change to satisfy labor law audits."

### Prompt 6: Labor Law & Compliance Guard
"Develop a policy engine that enforces regional labor laws (e.g., Mandatory breaks, Maximum daily/weekly hours). The system should automatically flag 'Compliance Risks' where a user works more than 12 hours in a 24-hour period."

## Integration & specialized Workflows
### Prompt 7: Seamless Payroll & Accounting Bridge
"Design an integration API that exports approved time data directly into common payroll systems and accounting ledgers (e.g., ADP, Quickbooks, or internal ERP). Support 'Cost-Center' and 'Job-Code' mapping for accurate financial allocation."

### Prompt 8: Geofenced 'Check-in' for Field Work
"Create a mobile service that supports geofenced clock-in. A user can only start a timer for a specific 'Client Site' if their GPS coordinates are within 100 meters of the site. automatically stop the timer if the user leaves the geofence."

## Analytics & specialized Features
### Prompt 9: Team Productivity & Velocity Dashboard
"Create a data visualization dashboard tracking 'Billable vs. Non-Billable Hours', 'Average Task Duration', and 'Team Utilization Rate'. Provide drill-down reports per project and individual employee."

### Prompt 10: AI-Powered Time Entry Categorizer
"Develop an AI service that analyzes descriptive time entry notes (e.g., 'Weekly meeting about project X') and automatically suggests the most likely 'Task Category' and 'Project Code' using an LLM or NLP model."

---
[← Previous: Roadmap & Future Enhancements](13-future-features.md) | [Back to Index](README.md) | [Next: Task Status →](15-task-status.md)
