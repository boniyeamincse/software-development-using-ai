# 07 - Library API Design

## Cataloging & Search
- `GET /api/v1/catalog/search`: Faceted product search with relevance ranking.
- `GET /api/v1/books/:isbn`: Fetch detailed metadata and availability status.

## Circulation Operations
- `POST /api/v1/loan/checkout`: Link a member ID to an item barcode.
- `PATCH /api/v1/loan/return`: Record return and trigger fine calculation.
- `POST /api/v1/holds/place`: Add student to the reservation queue.

## Member Services
- `GET /api/v1/member/loans`: List current borrowings and due dates.
- `POST /api/v1/member/fines/pay`: Integration with school payment gateway.

## Hardware Integration (Internal)
- `POST /api/v1/hardware/scan`: Receive RFID tag batches for automated audit.

---
[← Previous: Database Design](06-database-design.md) | [Back to Index](README.md) | [Next: UI Pages →](08-ui-pages.md)
