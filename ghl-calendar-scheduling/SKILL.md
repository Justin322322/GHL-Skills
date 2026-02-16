---
name: GHL Calendar & Scheduling
description: Guide for GoHighLevel calendar system — calendar types, booking widgets, round robin, availability, appointment notifications, and reminders.
---

# GHL Calendar & Scheduling

## Overview

GoHighLevel's calendar system handles appointment booking, team scheduling, and automated reminders. It integrates directly with the CRM, workflows, and AI agents for end-to-end appointment management.

---

## Calendar Types

| Type                    | Description                                        | Best For                                   |
| ----------------------- | -------------------------------------------------- | ------------------------------------------ |
| **Simple Calendar**     | Single user, single service                        | Solo practitioners, 1-on-1 consultations   |
| **Round Robin**         | Auto-distributes bookings among team members       | Sales teams, support teams                 |
| **Class Booking**       | Multiple attendees per time slot                   | Group sessions, webinars, classes          |
| **Collective Calendar** | Finds time when all selected team members are free | Multi-person meetings, panel interviews    |
| **Service Calendar**    | Offers multiple services with different durations  | Multi-service businesses (salons, clinics) |

---

## Calendar Setup

### Step-by-Step

1. **Create Calendar**: Settings → Calendars → Create Calendar
2. **Select Type**: Choose from Simple, Round Robin, Class, Collective, or Service
3. **Configure Details:**
   - Calendar name
   - Description
   - Duration options (15, 30, 45, 60 min)
   - Buffer time between appointments
   - Minimum scheduling notice

4. **Set Availability:**
   - Define available days and hours
   - Set timezone handling
   - Add blocked dates (holidays, vacations)
   - Configure recurring availability patterns

5. **Customize Booking Form:**
   - Required fields (name, email, phone)
   - Custom questions
   - Terms & conditions checkbox
   - File upload options

6. **Connect Integrations:**
   - Google Calendar sync (2-way)
   - Outlook Calendar sync
   - Zoom/Google Meet auto-link generation

### Availability Configuration

```
Monday:    9:00 AM – 5:00 PM
Tuesday:   9:00 AM – 5:00 PM
Wednesday: 9:00 AM – 12:00 PM (half day)
Thursday:  9:00 AM – 5:00 PM
Friday:    9:00 AM – 3:00 PM
Saturday:  Unavailable
Sunday:    Unavailable

Buffer: 15 min between appointments
Min Notice: 2 hours
Max Booking Window: 30 days ahead
```

---

## Round Robin Configuration

### Setup

1. Add team members to the calendar
2. Select distribution method:
   - **Equal Distribution**: Evenly distributes across all available members
   - **Priority Based**: Assigns based on member priority/weight
   - **Availability Based**: Assigns to next available member

3. Configure per-member availability (individual overrides)
4. Set reassignment rules for cancellations

### Best Practices

1. **Keep teams balanced** — Distribute evenly to prevent burnout
2. **Set individual availability** — Each team member manages their own schedule
3. **Configure fallbacks** — What happens if all members are booked?
4. **Track per-member metrics** — Monitor show rates by team member

---

## Booking Widget

### Embedding Options

| Method                 | Use Case                                   |
| ---------------------- | ------------------------------------------ |
| **Direct Link**        | Share via email, SMS, social media         |
| **Embedded iframe**    | Add to your website or funnel page         |
| **GHL Funnel Element** | Drag-and-drop calendar into a funnel page  |
| **Chat/AI Booking**    | AI books appointments during conversations |

### Widget Customization

- Brand colors and styling
- Custom header text
- Available slot display format
- Timezone auto-detection
- Confirmation page redirect

### Embed Code Example

```html
<iframe
  src="https://api.leadconnectorhq.com/widget/booking/{calendarId}"
  style="width:100%; border:none; overflow:hidden;"
  scrolling="no"
  id="booking-widget"
></iframe>
```

---

## Appointment Status Workflow

```
Booked → Confirmed → Showed / No-Show → Completed / Rescheduled / Cancelled
```

### Status-Based Automations

| Status Change   | Triggered Action                                          |
| --------------- | --------------------------------------------------------- |
| **Booked**      | Send confirmation email/SMS, create opportunity           |
| **Confirmed**   | Send prep materials, internal notification                |
| **24hr Before** | Send reminder SMS with meeting details                    |
| **1hr Before**  | Send final reminder with Zoom/location link               |
| **No-Show**     | Send reschedule link, internal alert                      |
| **Completed**   | Send follow-up email, review request, move pipeline stage |
| **Cancelled**   | Send re-engagement message, update pipeline               |

---

## Reminder Sequences

### Recommended Reminder Schedule

| Timing               | Channel | Message Example                                                  |
| -------------------- | ------- | ---------------------------------------------------------------- |
| **Immediately**      | Email   | Confirmation with all details (date, time, location/link)        |
| **24 hours before**  | SMS     | "Reminder: Your appointment is tomorrow at {{appointment.time}}" |
| **1 hour before**    | SMS     | "See you in 1 hour! Join here: {{appointment.meeting_link}}"     |
| **Post-appointment** | Email   | Thank you + next steps + review request                          |

### No-Show Recovery

```
Trigger: Appointment Status → No-Show
→ Wait 15 min
→ Send SMS: "We missed you! Would you like to reschedule? {{booking_link}}"
→ Wait 24 hours
→ If/Else: Rebooked?
   → Yes: End
   → No: Send Email with reschedule link + incentive
→ Wait 3 days
→ Final SMS: Last chance to reschedule
```

---

## Calendar Best Practices

1. **Always confirm appointments** — Send immediate confirmation via SMS and email
2. **Use buffer time** — 10-15 min between appointments prevents overlap stress
3. **Set minimum notice** — At least 2 hours prevents last-minute chaos
4. **Sync external calendars** — 2-way sync with Google/Outlook prevents double-booking
5. **Limit booking window** — 30-60 days ahead; too far out increases no-shows
6. **Add meeting links automatically** — Auto-generate Zoom/Google Meet links
7. **Track no-show rates** — Monitor and implement no-show recovery workflows
8. **Require phone number** — Enables SMS reminders, dramatically reduces no-shows
9. **Customize confirmation pages** — Redirect to a page with prep instructions

---

## Integration with AI

GHL's AI agents can book appointments during conversations:

1. Enable appointment booking in Voice AI or Conversation AI settings
2. Select the target calendar
3. AI suggests available slots to the lead
4. Lead confirms, and the appointment is automatically created
5. Standard confirmation + reminder workflows trigger

---

## Key Resources

- **Calendar Setup**: Settings → Calendars in sub-account
- **Google Calendar Sync**: Settings → Integrations → Google
- **Help Docs**: [GoHighLevel Calendar Guide](https://help.gohighlevel.com)
