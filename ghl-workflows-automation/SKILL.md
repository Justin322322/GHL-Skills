---
name: GHL Workflow Automation
description: Complete guide for GoHighLevel workflow builder — triggers, actions, conditional logic, custom values, naming conventions, and automation best practices.
---

# GHL Workflow Automation

## Overview

GoHighLevel's Workflow Builder is the automation engine powering all marketing, sales, and operational processes. Workflows replace the legacy "Campaigns" and provide a visual, drag-and-drop interface for building complex multi-step automations.

---

## Core Concepts

| Concept                 | Description                                                                        |
| ----------------------- | ---------------------------------------------------------------------------------- |
| **Trigger**             | The event that starts a workflow (e.g., form submitted, tag added)                 |
| **Action**              | The task performed after a trigger fires (e.g., send SMS, add tag)                 |
| **Condition (If/Else)** | Branching logic based on contact data, tags, or custom fields                      |
| **Wait Step**           | A timed delay between actions (minutes, hours, days, or specific time)             |
| **Goal**                | A target state that, when reached, stops the workflow for that contact             |
| **Custom Values**       | System-wide variables for dynamic content (e.g., `{{custom_values.company_name}}`) |
| **Custom Fields**       | Contact-specific data used in merge fields (e.g., `{{contact.first_name}}`)        |

---

## Triggers Reference

### Contact Events

- `Contact Created` — New contact added to the system
- `Contact Changed` — Any field on a contact is updated
- `Tag Added` / `Tag Removed` — Specific tag applied or removed
- `Contact DND` — Do Not Disturb status changed
- `Birthday Reminder` — Based on contact's birthday field
- `Note Added` / `Note Changed` — Internal notes activity

### Communication Events

- `Customer Replied` — Contact responds via any channel (email, SMS, etc.)
- `Form Submitted` — A specific GHL form is completed
- `Survey Submitted` — A specific survey is completed
- `Trigger Link Clicked` — Special tracking link is clicked
- `Email Events` — Email opened, clicked, bounced, complained, unsubscribed
- `Facebook Lead Form Submitted` — Lead ad form captured

### Sales & Booking Events

- `Appointment Status` — Booking confirmed, cancelled, no-showed
- `Pipeline Stage Changed` — Opportunity moves to a new stage
- `Opportunity Status Changed` — Deal won, lost, or abandoned
- `Order Submitted` / `Order Form Submission`
- `Invoice` — Invoice created, sent, paid, overdue
- `Payment Received`

### Membership Events

- `Membership New Signup`
- `Product Access Granted` / `Product Access Removed`
- `Offer Access Granted`
- `Category Completed` / `Product Completed`

### Other Events

- `Task Added` / `Task Completed` / `Task Reminder`
- `Stale Opportunities` — Opportunities inactive for a configured period
- `Inbound Webhook` — External systems trigger the workflow via webhook URL
- `Manual / API Trigger` — Workflow started manually or via API call

> **Best Practice**: Always apply **filters** to triggers. For example, filter a `Form Submitted` trigger to a specific form. Without filters, the workflow fires for ALL forms.

---

## Actions Reference

### Communication

- **Send Email** — HTML or plain text, with merge fields and attachments
- **Send SMS / MMS** — Text messages with optional media
- **Send Voicemail Drop** — Ringless voicemail delivery
- **Send to Messenger** — Facebook Messenger message
- **Send Internal Notification** — Alert team members via email or SMS
- **Send Review Request** — Automated review solicitation

### Contact Management

- **Add / Remove Tag**
- **Create / Update Contact**
- **Add to / Remove from Workflow**
- **Add Internal Note**
- **Create Task** — Assign follow-up tasks to team members
- **Assign User** — Assign contact to a specific team member
- **Update Custom Field** — Set or modify any custom field value
- **Math Operation** — Increment/decrement numeric fields (e.g., lead score)
- **Set Contact DND**

### Pipeline & Sales

- **Create / Update Opportunity**
- **Move Opportunity Stage**
- **Add to / Remove from Campaign**

### External & Advanced

- **Webhook (Custom)** — Send data to external systems (Zapier, Make, custom endpoints)
- **HTTP Request** — Make API calls to third-party services
- **Google Sheets** — Add rows, update cells
- **If / Else Condition** — Branch logic based on data
- **Go To Step** — Jump to a different action in the workflow
- **Wait** — Delay for a specified time or until a specific day/time

---

## Custom Values vs. Custom Fields

| Feature          | Custom Values                          | Custom Fields                       |
| ---------------- | -------------------------------------- | ----------------------------------- |
| **Scope**        | System-wide (same for everyone)        | Per-contact (unique to each person) |
| **Use Case**     | Company name, phone, address, branding | Contact name, email, lead score     |
| **Update**       | Change once → updates everywhere       | Changes per individual contact      |
| **Merge Syntax** | `{{custom_values.field_name}}`         | `{{contact.field_name}}`            |
| **Best For**     | Snapshots, templates, global branding  | Personalization, segmentation       |

### Custom Values Best Practices

1. **Group by category** — Create folders like "Business Info", "Branding", "Social Links"
2. **Use for snapshots** — Store client-specific details that can be easily swapped
3. **Naming convention** — Use `snake_case` with clear prefixes (e.g., `biz_phone`, `biz_email`)
4. **Keep them current** — Review and update quarterly

---

## Workflow Design Best Practices

### Planning

1. **Map the journey first** — Sketch the trigger → action flow on paper before building
2. **Start simple** — Begin with 3-5 steps, then add complexity
3. **One trigger per workflow** — Avoid multiple triggers causing confusion
4. **Use descriptive names** — Name workflows clearly: `[Niche] - [Purpose] - [Channel]` (e.g., `Dental - New Lead Follow-Up - SMS`)

### Building

1. **Use if/else branches** — Personalize paths based on tags, custom fields, or contact behavior
2. **Add wait steps** — Space out messages naturally (don't send 5 SMS in 1 minute)
3. **Set time windows** — Configure delivery hours (e.g., 9 AM–6 PM in contact's timezone)
4. **Use goals** — Stop the workflow when the desired outcome is achieved (e.g., appointment booked)
5. **Add internal notifications** — Alert team members at critical workflow points

### Testing

1. **Test with a real contact** — Create a test contact and run through the entire workflow
2. **Verify all links** — Check every URL, tracking link, and redirect
3. **Check merge fields** — Ensure all `{{variables}}` resolve correctly
4. **Test edge cases** — Verify if/else branches with different contact data
5. **Monitor after launch** — Watch the first 10-20 enrollments for errors

### Performance

1. **Review weekly** — Check open rates, click rates, and reply rates
2. **A/B test messages** — Experiment with different copy, subject lines, and timing
3. **Archive unused workflows** — Deactivate and archive workflows no longer in use
4. **Document your automations** — Maintain an internal wiki or spreadsheet listing all active workflows

---

## Common Workflow Templates

### Speed-to-Lead (New Lead Response)

```
Trigger: Form Submitted
→ Send SMS (Immediate): "Thanks {{contact.first_name}}! We'll be in touch shortly."
→ Send Email: Welcome + value proposition
→ Internal Notification: Alert sales rep
→ Wait 5 min
→ If/Else: Contact replied?
   → Yes: End workflow
   → No: Send SMS follow-up
→ Wait 24 hours
→ Send Email: Case study / testimonial
→ Wait 48 hours
→ If/Else: Appointment booked?
   → Yes: End workflow
   → No: Send SMS with booking link
```

### Appointment Reminder Sequence

```
Trigger: Appointment Status → Confirmed
→ Send SMS: "Your appointment is confirmed for {{appointment.date}}!"
→ Wait until 24hrs before appointment
→ Send SMS: "Reminder: Your appointment is tomorrow at {{appointment.time}}"
→ Wait until 1hr before appointment
→ Send SMS: "See you in 1 hour! Here's the address: {{custom_values.biz_address}}"
```

### Review Request Automation

```
Trigger: Pipeline Stage Changed → "Completed" / "Delivered"
→ Wait 2 days
→ Send SMS: "How was your experience? We'd love a review! {{custom_values.review_link}}"
→ Wait 3 days
→ If/Else: Review received?
   → Yes: Send thank you SMS
   → No: Send Email: Gentle review reminder
```

---

## Key Resources

- **Official Help**: [Workflow Actions Reference](https://help.gohighlevel.com)
- **Templates**: Available in the GHL Marketplace
- **Community**: [GHL Ideas Board](https://ideas.gohighlevel.com) for feature requests
