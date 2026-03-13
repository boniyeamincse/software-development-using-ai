# 14 - Project Management Solution Development Prompts

## Project Orchestration & Planning
### Prompt 1: High-Performance Gantt Chart Engine
"Design a PostgreSQL schema for a project management system that supports deeply nested tasks and dependencies (Finish-to-Start, Start-to-Start). Implement an algorithm that calculates the 'Critical Path' and automatically adjusts dates across the entire project when a parent task is moved."

### Prompt 2: Dynamic Kanban with Custom Workflow Logic
"Develop a React component for a Kanban board that supports custom 'Columns' and 'WIP (Work In Progress) Limits'. Implement a 'Policy Engine' that prevents moving a card to 'Done' unless a specifically required 'Checklist' is 100% complete."

## Collaboration & Communication
### Prompt 3: Real-time Multi-User Document Collaborative Editor
"Create an architecture for a real-time collaborative documentation tool (similar to Notion). Use CRDTs (Conflict-free Replicated Data Types) or Operational Transformation (OT) to ensure data consistency across multiple active users. support rich-text formatting and @mentions."

### Prompt 4: Integrated Project Discussion Hub
"Develop a communication service that aggregates discussions, comments, and file attachments per task. Implement 'Threaded Replies' and real-time notifications (via WebSockets) to keep team members aligned without leaving the project context."

## Resource & Time Management
### Prompt 5: Advanced Resource Allocation & Workload Balancer
"Design a service that tracks 'Team Capacity' versus 'Assigned Work'. Implement a 'Heatmap' visualization that identifies over-burdened team members and suggests 'Auto-Reassignment' based on member skills and current availability."

### Prompt 6: Intelligent Time-Tracking & Billing Bridge
"Develop a service that converts tracked time directly into billable invoices. Support 'Tiered Hourly Rates' for different roles and 'Fixed-Fee' milestones. Automatically flag 'Timesheet Discrepancies' where tracked time exceeds estimated time by more than 20%."

## Trust, Privacy & Audit
### Prompt 7: Immutable Project Audit Transaction Vault
"Design a secure, write-once-read-many (WORM) audit log for all project changes. every status update, deadline shift, and user assignment must be hashed and stored to ensure a permanent, tamper-proof project history for compliance."

### Prompt 8: Enterprise-Grade RBAC & External Guest Access
"Implement a complex RBAC system that supports 'Internal Team Members' and 'External Guest/Client' roles. Ensure that Guests can only see tasks specifically tagged for 'Client Visibility' and cannot access internal project discussions or financial data."

## Analytics & specialized Features
### Prompt 9: Executive Project Portfolio (PPM) Dashboard
"Create a data visualization dashboard tracking 'Portfolio Health', 'Budget Variance (planned vs. actual)', and 'Strategic Alignment'. Provide drill-down reports for individual project managers and departments."

### Prompt 10: AI-Powered Project Delay Predictor
"Develop a forecasting model that analyzes historical project data (previous delays, team velocity, task complexity). Predict the likely 'Completion Date' for an active project and alert stakeholders if the project is 'At Risk' of missing a major milestone."

---
[← Previous: Roadmap & Future Enhancements](13-future-features.md) | [Back to Index](README.md) | [Next: Task Status →](15-task-status.md)
