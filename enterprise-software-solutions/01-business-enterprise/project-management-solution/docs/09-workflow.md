# 09 - Project System Workflows

## The Project Lifecycle (Kickoff to Closing)
1. **Initiation**: Project Manager selects a "Standard Tech Launch" template.
2. **Scheduling**: PM defines milestones and links tasks via the Gantt builder.
3. **Allocation**: System suggests best-fit team members based on skills and availability.
4. **Execution**: Team members move tasks through the Kanban board and log time.
5. **Monitoring**: Automated "Daily Digest" identifies tasks that are past due.
6. **Closing**: Final deliverables approved; Retrospective notes logged; Team capacity released.

## Dependency Resolution Workflow
1. Task B is dependent on Task A (Finish-to-Start).
2. Developer delays Task A by 3 days.
3. System automatically calculates the downstream impact on Task B and all linked milestones.
4. Notification sent to PM: "Schedule conflict detected in Milestone X."
5. PM chooses "Auto-Realign" to shift the entire project schedule forward.

## Status Reporting Workflow
1. Every Friday at 4 PM, system aggregates task progress and budget data.
2. AI summarizes the "Risk Level" based on velocity trends.
3. Professional PDF report is drafted and sent to the PM for review.
4. Once approved, it is automatically distributed to the Stakeholder list.
