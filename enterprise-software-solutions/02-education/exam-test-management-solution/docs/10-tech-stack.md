# 10 - Exam Technology Stack

## Core Engine
- **Backend**: Python (FastAPI) for high-performance IO.
- **AI/ML**: Python (OpenCV / TensorFlow) for proctoring analysis.
- **Frontend**: Vue.js (Lightweight and fast for low-bandwidth CBT).

## Security & Storage
- **Vault**: For managing encryption keys.
- **S3**: Question paper storage with Lifecycle policies (auto-delete after 1 year).
- **PostgreSQL**: Transactional database.

## Networking
- **WebSocket (WSS)**: For real-time proctoring alerts.
- **Cloudflare Warp**: For secure tunnel routing from test centers.
