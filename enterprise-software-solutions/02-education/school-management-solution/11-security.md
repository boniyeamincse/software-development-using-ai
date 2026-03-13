# 11 - Security & Compliance

## Security Measures
- **Encryption**: AES-256 for data at rest (S3/PostgreSQL); TLS 1.3 for data in transit.
- **Authentication**: JWT-based stateless authentication with MFA support.
- **Authorization**: Granular RBAC (Role-Based Access Control) for all endpoints.
- **API Security**: Rate limiting and CORS protection.
- **Audit Logs**: Comprehensive logging of sensitive actions (e.g., grade changes, fee overrides).

## Compliance
- **GDPR**: Tools for data portability and the "Right to be Forgotten".
- **FERPA**: Adherence to Student Privacy regulations.
- **Backups**: Daily encrypted backups with multi-region replication.
