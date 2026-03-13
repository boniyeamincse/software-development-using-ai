# 06 - Compliance Database Design

## Core Schema Components

### 1. Frameworks & Requirements
- `framework_id`, `name` (e.g., SOC2), `version`, `description`
- `requirement_id`, `framework_id`, `code` (e.g., CC1.1), `description`

### 2. Policies & Attestations
- `policy_id`, `title`, `current_version`, `status` (Draft/Active/Retired)
- `attestation_id`, `user_id`, `policy_id`, `version_signed`, `timestamp`

### 3. Controls & Evidence
- `control_id`, `name`, `frequency` (e.g., Daily/Annual), `status` (Pass/Fail)
- `evidence_id`, `control_id`, `s3_url`, `collected_at`, `source_type` (Auto/Manual)

### 4. Risks & Incidents
- `risk_id`, `description`, `likelihood`, `impact`, `score`, `owner_id`
- `incident_id`, `title`, `severity`, `status` (Open/Investigating/Resolved)

## Key Relationships
- **Many-to-Many**: One Requirement can be met by multiple Controls; One Control can satisfy multiple Requirements.
- **One-to-Many**: One Policy has many historical Versions.
- **Many-to-One**: Many Incident reports can stem from one identified Compliance Risk.

---
[← Previous: System Architecture](05-system-architecture.md) | [Back to Index](README.md) | [Next: API Design →](07-api-design.md)
