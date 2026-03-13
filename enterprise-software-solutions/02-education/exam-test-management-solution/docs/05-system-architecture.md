# 05 - Exam System Architecture

## Resilience and Security
The system is built on a **Stateless API Architecture** with optimized heavy-load handling for peak exam times.

## Component Breakdown
- **Secure Browser Sandbox**: A client-side wrapper that locks the student's device.
- **Edge API Gateway**: Protects against DDoS attacks and manages rate-limiting.
- **Worker Clusters**: Dedicated servers for CPU-intensive tasks like OMR image processing or AI proctoring video analysis.
- **Real-time Sync (Socket.io)**: Ensures student progress is saved locally and synced to the server instantly.

## Data Infrastructure
- **Encrypted Blob Storage**: For storing sensitive question papers.
- **In-Memory Cache (Redis)**: Store active exam states for ultra-fast recovery if a student's session breaks.
- **Primary Database**: ACID-compliant RDBMS for final grades and student records.
