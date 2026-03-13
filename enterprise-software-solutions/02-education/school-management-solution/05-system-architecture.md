# 05 - System Architecture

## Overview
The system follows a **Cloud-Native Microwe-service Architecture** to ensure scalability and high availability.

## Frontend
- **Web App**: Built with React.js for a responsive, single-page application experience.
- **Mobile App**: Developed using React Native for a consistent cross-platform experience (iOS/Android).

## Backend
- **Node.js (Express)**: Handles business logic and API orchestration.
- **RESTful API**: Standardized communication between frontend and backend.

## Data Tier
- **PostgreSQL**: Relational database for structured data like student records and financial transactions.
- **Redis**: Caching layer for session management and fast retrieval of frequent queries.

## Integration Layer
- **AWS S3**: Secure storage for student documents and uploaded media.
- **Twilio/SendGrid**: Integration for SMS and Email notifications.
