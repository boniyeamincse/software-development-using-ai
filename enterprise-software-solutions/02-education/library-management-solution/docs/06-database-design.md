# 06 - Library Database Design

## Core Schema Components

### 1. Catalog & Items
- `book_id`, `isbn`, `title`, `author`, `publisher`, `publication_date`
- `item_instance_id`, `book_id`, `barcode_id`, `rfid_tag`, `status` (Available/Loaned/Lost)

### 2. Circulation
- `loan_id`, `item_instance_id`, `member_id`, `checkout_date`, `due_date`, `return_date`

### 3. Fines & Transactions
- `fine_id`, `loan_id`, `amount`, `status` (Unpaid/Paid), `reason`

### 4. Holds & Reservations
- `hold_id`, `book_id`, `member_id`, `queue_position`, `expires_at`

## Key Relationships
- **One-to-Many**: One Book (Title) can have many Item Instances (Physical Copies).
- **One-to-Many**: One Member can have multiple active Loans.

---
[← Previous: System Architecture](05-system-architecture.md) | [Back to Index](README.md) | [Next: API Design →](07-api-design.md)
