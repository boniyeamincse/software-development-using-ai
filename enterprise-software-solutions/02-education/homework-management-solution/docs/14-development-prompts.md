# 14 - Homework Management Development Prompts

## Assignment Orchestration
### Prompt 1: Multi-Media Submission Schema
"Design a PostgreSQL schema for student homework submissions. The schema must support diverse file types (PDF, Images, Code, Video links), handle multiple versions/resubmissions, and track metadata like 'Late Status' and 'Originality Score'. Include a table for `rubric_scores` linked to specific grading criteria."

### Prompt 2: Deadline Escalation Service
"Implement a background worker service in Go or Python that monitors upcoming homework deadlines. The service should send automated warnings 24 hours before a deadline, immediate alerts for missed deadlines, and handle grace periods configured per assignment."

## Grading & Feedback
### Prompt 3: AI-Assisted Feedback Generator
"Develop a tool that integrates with a Large Language Model (e.g., GPT-4 or Claude) to provide preliminary feedback on student text submissions based on a teacher-provided rubric. The AI output must be presented as a 'Draft Comment' for teacher review, not a final grade."

### Prompt 4: Annotation & Markup API
"Design an API for an in-browser annotation tool. Students and teachers should be able to highlight specific text or areas on a PDF submission and attach threaded comments. Support real-time updates using WebSockets for collaborative feedback sessions."

## Integrity & Analytics
### Prompt 5: Plagiarism Check Pipeline
"Create a data pipeline that integrates with plagiarism detection services (e.g., Turnitin or Copyleaks). Implement a workflow where every submission is automatically sent for scanning, and the resulting 'Similarity Report' is linked back to the student's submission record."

### Prompt 6: Homework Engagement Insights
"Develop a dashboard query that calculates 'Effort Metrics' per student. Analyze time spent on the assignment portal, number of draft saves, and resource downloads. Correlate this data with final grades to identify students who are struggling despite high effort."

## student Workspace
### Prompt 7: Offline-First Homework App
"Design the architecture for an offline-first mobile app using React Native and WatermelonDB. Students should be able to download assignment instructions, work on their homework offline, and have the system automatically sync and submit once back online."

### Prompt 8: Peer-Feedback Matching Logic
"Build a module for 'Anonymous Peer Review'. Implement logic to randomly (or criteria-based) assign homework to 3 peers for feedback. Ensure absolute anonymity and allow the teacher to override or moderate peer-given scores."

## Teacher Tools
### Prompt 9: Bulk Grading Interface
"Create a UI component for 'Speed Grading'. The interface should allow teachers to quickly cycle through submissions, apply common feedback checkboxes, and enter scores using keyboard shortcuts. Integrate with the annotation API for deep-dives."

### Prompt 10: Parent Progress Digest
"Develop a weekly automation that compiles a 'Homework Digest' for parents. Include list of completed assignments, upcoming deadlines, and specific areas where the teacher has noted the student needs improvement."

---
[← Previous: Roadmap & Future Enhancements](13-future-features.md) | [Back to Index](README.md) | [Next: Task Status →](15-task-status.md)
