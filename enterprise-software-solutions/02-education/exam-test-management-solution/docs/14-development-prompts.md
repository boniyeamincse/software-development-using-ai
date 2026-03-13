# 14 - Exam & Test Management Development Prompts

## Core Exam Engine
### Prompt 1: Secure Question Bank Schema
"Design a secure PostgreSQL schema for a large-scale Question Bank. Support multiple question types (MCQ, Multi-select, Integer, Subjective, Matching). Include support for metadata like difficulty level, Bloom's Taxonomy category, and learning objective mapping. Ensure performance for fetching 100 random questions from a pool of 10,000+."

### Prompt 2: Adaptive Testing Algorithm
"Implement a basic Computer Adaptive Testing (CAT) algorithm in Python. The algorithm should adjust the difficulty of the next question based on the student's previous answers, aiming to pinpoint their ability level with the fewest questions possible. Include simulations for various student performance profiles."

## Examination Workflows
### Prompt 3: Timed Exam Session Handler
"Develop a WebSocket-based service to manage real-time timed exam sessions. The service must handle periodic auto-saves of student responses, provide an accurate 'Time Remaining' countdown synced with the server, and automatically submit the exam when the time expires or if the student's session is terminated."

### Prompt 4: Bulk Question Import Engine
"Write a parser that allows teachers to bulk-upload questions from Excel/CSV or LaTeX formats. Implement strict validation for question structure, option counts, and correct answer flags. Provide a preview UI that highlights any formatting errors before final database insertion."

## Integrity & Security
### Prompt 5: AI Proctoring Event Logger
"Create an API to receive and log events from an AI proctoring client (e.g., eye-tracking anomalies, person count changes, background noise). Implement an 'Aggregated Risk Score' for each student session that triggers an alert for human review if it crosses a configurable threshold."

### Prompt 6: Secure Exam Browser Config Generator
"Develop a tool that generates configuration files for the Safe Exam Browser (SEB). Ensure that the config forces the browser to lock down the operating system, restricts access to external URLs, and requires a specific 'Exam Password' provided only by authorized proctors."

## Results & Analytics
### Prompt 7: Automated MCQ Grading Service
"Implement a high-performance service to grade objective (MCQ) exams immediately upon submission. Ensure the service handles 'Negative Marking' schemes and partial credit for multi-select questions. Calculate percentile rankings against the current cohort in real-time."

### Prompt 8: Peer Review Assignment Logic
"For subjective exams, build an algorithm that anonymously assigns student work to peer reviewers. Support 'Calibrated Peer Review' where students must grade a set of 'control' answers before they are allowed to grade their peers' work."

## Administration & Reporting
### Prompt 9: Seat Plan Generator
"Develop an algorithm to generate optimal exam seat plans for large halls. The plan should maximize physical distance between students taking the same exam and accommodate students with special accessibility needs. Output a PDF map of the hall layout."

### Prompt 10: Institutional Performance Report
"Create a summary report for school administrators that compares performance across different subjects, classes, and teachers. Identify 'Outlier' questions where the majority of high-performing students failed, indicating a potential issue with question clarity or curriculum alignment."
