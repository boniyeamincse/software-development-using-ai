# 10 - Clinic Technology Stack

## Core Development
- **Backend API**: Node.js (TypeScript) or Go.
- **Frontend**: React (Clinic) and Flutter (Mobile).
- **Styling**: Tailwind CSS for a modern, responsive administrative UI.

## Healthcare & Communications
- **Interoperability**: FHIR API for data exchange.
- **E-Prescribing**: Integration with Surescripts or DoseSpot.
- **Notifications**: Twilio (SMS) and SendGrid (Email).

## Infrastructure & Database
- **Primary DB**: AWS Aurora PostgreSQL (Serverless).
- **File Storage**: AWS S3 for patient documents and uploaded ID cards.
- **Logging**: Amazon CloudWatch for immutable audit trail capture.

## Deployment
- **Platform**: Vercel (Frontend) and AWS Lambda (Backend).
- **CI/CD**: GitHub Actions for automated testing and deployment.
