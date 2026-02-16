---
name: GHL CRM, Contacts & Pipeline Management
description: Comprehensive guide for GoHighLevel CRM — contact management, tagging, custom fields, smart lists, pipeline stages, opportunity tracking, and lead scoring.
---

# GHL CRM, Contacts & Pipeline Management

## Overview

GoHighLevel's CRM is the central hub for all customer data, sales pipelines, and deal tracking. Master these concepts to build efficient lead-to-close systems.

---

## Contact Management

### Core Concepts

| Concept                  | Description                                                                      |
| ------------------------ | -------------------------------------------------------------------------------- |
| **Contacts**             | Individual records representing leads, prospects, or clients                     |
| **Tags**                 | Labels for categorizing and segmenting contacts (e.g., `hot-lead`, `vip-client`) |
| **Custom Fields**        | User-defined data points beyond defaults (e.g., "Company Size", "Budget Range")  |
| **Smart Lists**          | Dynamic, filter-based lists that auto-update based on criteria                   |
| **DND (Do Not Disturb)** | Per-channel communication opt-out settings                                       |

### Best Practices

1. **Clean your database regularly** — Remove duplicates and outdated contacts monthly
2. **Use a tagging system** — Create a naming convention (e.g., `source:facebook`, `status:qualified`, `industry:dental`)
3. **Segment by behavior** — Group contacts by actions taken (form submitted, link clicked, appointment booked)
4. **Leverage custom fields wisely** — Only add fields you will actually use in automations or reporting
5. **Import properly** — Format CSVs with proper column mapping before import; merge duplicates on import
6. **Use bulk actions** — Update tags, pipelines, DND status, and enrollments in bulk for efficiency

### Contact Lifecycle Stages

```
Lead → MQL (Marketing Qualified) → SQL (Sales Qualified) → Opportunity → Customer → Advocate
```

Map these stages using **tags** or **pipeline stages** to track progression.

### Smart List Filters

Commonly used filters for building smart lists:

- **Tag is/is not** — Filter by tag presence
- **Last activity** — Find stale contacts (e.g., no activity in 30+ days)
- **Source** — Segment by lead origin (Facebook, Google, referral)
- **Custom field values** — Filter by any custom field data
- **Assigned user** — View contacts owned by specific team members

---

## Pipeline Management

### Pipeline Design Principles

1. **Keep stages simple** — Use ≤ 7 stages with clear, action-oriented names
2. **Stages should be definitive** — A contact should clearly belong to one stage
3. **Move left-to-right** — Stages should represent forward progress
4. **Include a lost/closed stage** — Always track disqualified or churned opportunities

### Recommended Pipeline Templates

#### Sales Pipeline

```
New Lead → Contacted → Qualified → Proposal Sent → Negotiation → Closed Won / Closed Lost
```

#### Client Onboarding Pipeline

```
Signed → Kickoff Scheduled → Onboarding In Progress → Training → Delivered → Active Client
```

#### Recruitment Pipeline

```
Applied → Screening → Interview → Offer → Hired / Rejected
```

### Pipeline Best Practices

- **Update daily** — Move opportunities to the correct stage each day
- **Automate stage transitions** — Use workflows to move contacts when they book calls, reply, or submit forms
- **Assign owners** — Every opportunity should have an assigned team member
- **Set deal values** — Always estimate the opportunity value for forecasting
- **Use pipeline-driven automations** — Trigger follow-ups, notifications, and tasks based on stage changes

---

## Opportunity Management

### Creating Opportunities

Opportunities can be created:

- **Manually** — From the contact record or opportunities view
- **Via workflow** — Automatically on form submission, tag addition, or appointment booking
- **Via API** — Programmatically through the API v2

### Opportunity Fields

| Field        | Purpose                                    |
| ------------ | ------------------------------------------ |
| **Name**     | Descriptive title for the deal             |
| **Pipeline** | Which pipeline this opportunity belongs to |
| **Stage**    | Current position in the pipeline           |
| **Value**    | Estimated monetary value                   |
| **Owner**    | Assigned sales rep or team member          |
| **Status**   | Open, Won, Lost, or Abandoned              |
| **Source**   | Origin of the lead                         |

### Best Practices

1. **Standardize naming** — Use a convention like `[Contact Name] - [Service]` for opportunity names
2. **Track lost reasons** — Always log why opportunities are lost for analysis
3. **Implement lead scoring** — Score contacts based on engagement to prioritize high-value deals
4. **Use round robin** — Distribute new opportunities evenly across sales reps
5. **Add contextual notes** — Record key details from calls and meetings on the opportunity card

---

## Lead Scoring

GoHighLevel supports lead scoring to prioritize the most engaged contacts.

### Scoring Factors

| Action                | Suggested Points |
| --------------------- | ---------------- |
| Form submitted        | +10              |
| Email opened          | +2               |
| Link clicked          | +5               |
| Appointment booked    | +15              |
| Replied to message    | +10              |
| Visited pricing page  | +8               |
| No activity (30 days) | -5               |

### Implementation

1. Create a custom field `Lead Score` (number type)
2. Use workflow actions to increment/decrement the score
3. Set up smart lists filtering by score thresholds (e.g., Score ≥ 30 = Hot Lead)
4. Trigger notifications when contacts hit high-score thresholds

---

## Key Resources

- **Official Docs**: [GoHighLevel Help Center](https://help.gohighlevel.com)
- **API Reference**: [Marketplace API Docs](https://marketplace.gohighlevel.com/docs/)
- **Community**: [GoHighLevel Facebook Group](https://www.facebook.com/groups/gohighlevel)
