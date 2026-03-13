# 14 - Tutoring Marketplace Development Prompts

## Marketplace Mechanics
### Prompt 1: Matching Algorithm for Tutors/Students
"Develop a Python matching algorithm that pairs students with tutors based on subject matter expertise, availability overlaps, budget constraints, and geographical proximity (for in-person) or time zone compatibility (for online). Include a ranking system that prioritizes tutors with higher 'Success Scores' and faster response times."

### Prompt 2: Dynamic Pricing Engine
"Implement a Node.js service for a dynamic pricing engine. Tutors should be able to set base rates, but the system should suggest adjustments based on current market demand for a subject, tutor experience levels, and package discounts (e.g., 10% off for 5 sessions). Handle currency conversion for cross-border tutoring."

## Communication & Engagement
### Prompt 3: Real-Time Interactive Classroom
"Design the architecture for an interactive virtual classroom using WebRTC and WebSockets. Include features for a shared low-latency whiteboard, real-time code editor integration (e.g., Monaco Editor), and file sharing. Ensure high-quality video/audio streaming with automatic quality adjustment based on bandwidth."

### Prompt 4: Contextual Bidding System
"Create an API for a bidding system where students post 'Learning Requests' and tutors bid on them. Implement logic to prevent spam, allow students to 'Shortlist' tutors, and automatically close the request once a tutor is hired and a deposit is paid."

## trust & Safety
### Prompt 5: Background Check Integration
"Develop a secure integration with an external background check provider (e.g., Checkr or Sterling). Implement a status workflow where a tutor's profile is only marked 'Verified' after a successful check. Ensure PII sent to the provider is encrypted and never stored permanently in the local database."

### Prompt 6: AI Content Moderation for Profiles
"Implement a content moderation service using OpenAI's moderation API or similar to scan tutor profiles and student requests for inappropriate content, contact info sharing (to bypass platform fees), or prohibited academic services (e.g., 'Do my homework for me')."

## Finance & Payments
### Prompt 7: Escrow & Milestone Payments
"Build a payment orchestration service that implements an escrow system. Payments are collected from the student at the time of booking but only released to the tutor after the session is marked 'Complete' and no disputes are raised within 24 hours. Support partial milestone releases for long-term projects."

### Prompt 8: Commission & Tax Reporting
"Write a service to calculate platform commissions and generate monthly earnings reports for tutors. Include the ability to generate 1099-NEC forms (or regional equivalents) based on annual earnings and tax residency status."

## mobile & Notifications
### Prompt 9: Proactive Booking Reminders
"Develop a notification engine that sends multi-channel reminders (Push, SMS, Email) 1 hour before a session. Include deep-linking directly to the virtual classroom for the mobile app."

### Prompt 10: Tutor Availability Optimizer
"Create a UI component using React Big Calendar or similar that allows tutors to quickly set recurring availability and sync it with external calendars (Google, Outlook) using the Cronofy or Cal.com API."