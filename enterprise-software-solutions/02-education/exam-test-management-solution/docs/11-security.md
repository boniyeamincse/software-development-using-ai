# 11 - Exam Security & Integrity

## Integrity Measures
- **IP Whitelisting**: Restricting exam access to specific institutional CIDRs.
- **Randomization**: Shuffling questions and options differently for every student.
- **Digital Signatures**: Ensuring the result PDF is tamper-proof with institutional hashes.

## Infrastructure Security
- **Encryption at Rest**: PGP-encrypted question papers until 10 minutes before the exam starts.
- **Session Stickiness**: Ensuring a student stays connected to the same server node to prevent data race conditions during sync.
