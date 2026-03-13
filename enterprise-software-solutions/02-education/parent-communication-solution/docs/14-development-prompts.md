# 14 - Parent Communication Development Prompts

## Notification & Messaging
### Prompt 1: Multi-Channel Alert Engine
"Design a highly reliable Node.js service for sending school alerts via Push, SMS, and Email. The service must handle priority levels (Emergency vs. General), manage user preferences for each channel, and include a 'Read Receipt' tracking system for administrative audits."

### Prompt 2: Real-time Parent-Teacher Chat
"Implement a scalable chat architecture using WebSockets (Socket.io) and Redis for parent-teacher communication. Include features for message search, image attachments, and 'Office Hours' logic that automatically sets a status of 'Away' and provides a default response after hours."

## Engagement & Scheduling
### Prompt 3: PT Meeting Scheduling Algorithm
"Develop an algorithm to manage Parent-Teacher Meeting (PTM) blocks. Students have multiple teachers, and parents need to schedule short blocks with each. The algorithm should find the most efficient schedule that minimizes gaps for parents while staying within the teachers' available time slots."

### Prompt 4: Interactive School Event Calendar
"Create a React component for an interactive school event calendar. Support recurring events, event categories (Academic, Sports, Arts), and allow parents to sync specific events directly to their personal calendars (Google/iCal) via an ICS feed or API."

## Content & Transparency
### Prompt 5: Dynamic Progress Report PDF Generator
"Write a service using PDFKit or Puppeteer to generate professional, multi-page student progress reports. Aggregate data from SIS (Grades) and Attendance modules. Include interactive charts for trend analysis and a digital signature field for parents."

### Prompt 6: Multi-Language Translation Service
"Implement an automated translation layer for school-wide announcements. Integrate with Amazon Translate or Google Cloud Translation to translate announcements into the parent's preferred language (supporting 10+ common languages in the district) upon delivery."

## Security & Privacy
### Prompt 7: Family Unit Linking Schema
"Design a PostgreSQL schema that handles complex family relationships (Guardians, Step-parents, Emergency Contacts). Implement strict access control logic to ensure only legally authorized individuals can view specific student records (e.g., medical info vs. grade info)."

### Prompt 8: Photo Release & Privacy Consent Hub
"Build a module where parents can manage digital consent for their children, including photo releases, field trip permissions, and health screenings. Maintain a full audit trail of when consent was provided or revoked."

## Mobile App Features
### Prompt 9: Biometric Secure Login
"Develop the authentication flow for the Parent mobile app using Expo LocalAuthentication or similar. Implement biometric (FaceID/Fingerprint) login with a secure fallback to a PIN or password. Handle token refresh cycles to ensure security without frequent manual logins."

### Prompt 10: Geo-fenced Attendance Notifications
"Develop a service that sends an immediate notification to parents when a student enters or leaves the school campus, based on RFID or GPS geofencing. Include timestamp and exit/entry point details."

---
[← Previous: Roadmap & Future Enhancements](13-future-features.md) | [Back to Index](README.md) | [Next: Task Status →](15-task-status.md)
