# 06 - Customer Support Database Design

## Core Schema Components

### 1. Tickets & Conversations
- `ticket_id`, `subject`, `description`, `status` (Open/Solving/Closed), `priority`, `channel_id`, `assigned_agent_id`
- `message_id`, `ticket_id`, `sender_id`, `content_body`, `is_internal_note`, `timestamp`

### 2. Customers & Profiles
- `customer_id`, `external_id` (from CRM/Ecom), `name`, `email`, `phone`, `total_tickets_count`

### 3. Knowledge Base
- `article_id`, `category_id`, `title`, `content_html`, `author_id`, `is_published`

### 4. SLAs & Workflows
- `sla_policy_id`, `priority`, `response_time_minutes`, `resolution_time_minutes`

## Key Relationships
- **One-to-Many**: One Ticket contains multiple Messages.
- **Many-to-One**: Many Tickets belong to one Customer.
- **One-to-Many**: One SLA Policy applies to many Tickets of the same priority.
