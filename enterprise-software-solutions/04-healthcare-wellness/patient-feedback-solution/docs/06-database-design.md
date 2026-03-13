# 06 - Patient Feedback Database Design

## Core Schema Components

### 1. Survey Templates & Logic
- `template_id`, `name`, `type` (NPS/CSAT/HCAHPS), `version`, `questions_json`
- `logic_id`, `template_id`, `skip_logic_rules_json`

### 2. Survey Responses (Document Store)
- `response_id`, `template_id`, `source_encounter_id`, `patient_id` (Optional/Anonymized)
- `scores_json` ({ "NPS": 9, "Value": 5 }), `comment_txt`, `timestamp`

### 3. Sentiment & Analysis
- `analysis_id`, `response_id`, `overall_sentiment` (Positive/Neutral/Negative)
- `extracted_themes_json` ([ { "theme": "Wait Time", "sentiment": -0.8 } ])

### 4. Grievance & Case Management
- `case_id`, `response_id`, `designated_manager_id`, `status` (Open/Investigating/Resolved)
- `resolution_note`, `recovery_score`, `closed_at`

### 5. Facility Master Data
- `facility_id`, `department_id`, `staff_id`, `name`, `role`

## Key Relationships
- **Many-to-One**: Many Responses link to one Survey Template.
- **One-to-One**: One Response has one Sentiment Analysis document.
- **One-to-Many**: One Response may trigger one or more Case Management workflows.
- **One-to-Many**: One Facility has many Departments, which have many Staff members.
