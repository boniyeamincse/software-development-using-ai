# 06 - Pharmacy Database Design

## Core Schema Components

### 1. Medication Catalog (Drug Master)
- `drug_id`, `din` (Drug Identification Number), `name`, `active_ingredients`, `strength`, `manufacturer`
- `is_narcotic` (boolean), `storage_temp_range`, `unit_type` (Pill/Vial/ML)

### 2. Inventory & Stock
- `inventory_id`, `branch_id`, `drug_id`, `batch_number`, `expiry_date`
- `stock_on_hand`, `reorder_level`, `cost_price`, `selling_price`

### 3. Prescriptions & Dispensing
- `rx_id`, `patient_id`, `prescriber_id`, `drug_id`, `ordered_quantity`, `refills_allowed`
- `dispense_id`, `rx_id`, `filled_by_id`, `checked_by_id`, `quantity_filled`, `timestamp`

### 4. Narcotics Ledger (Immutable)
- `log_id`, `dispense_id`, `branch_id`, `action` (Dispense/Waster/Receive), `quantity`, `signatures_collected_json`

### 5. Insurance & Adjudication
- `claim_id`, `dispense_id`, `payer_id`, `response_code`, `approved_amount`, `patient_co_pay`

## Key Relationships
- **One-to-Many**: One Prescription (Rx) can have multiple Dispensing events (Refills).
- **Many-to-One**: Many Stock Batches link to one Drug Master record.
- **Many-to-Many**: Insurance Payers cover many Drugs with different copay tiers.
- **One-to-One**: Every Narcotic dispense event must link to a unique Ledger entry.
