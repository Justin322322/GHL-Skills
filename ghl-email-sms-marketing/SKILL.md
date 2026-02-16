---
name: GHL Email & SMS Marketing
description: Guide for GoHighLevel messaging — email campaigns, SMS sequences, unified inbox, WhatsApp, social DMs, templates, deliverability, and compliance.
---

# GHL Email & SMS Marketing

## Overview

GoHighLevel centralizes all communication channels into a unified inbox. This covers email marketing, SMS/MMS messaging, WhatsApp, social media DMs, and multi-channel campaign strategies.

---

## Unified Inbox

### Supported Channels

| Channel                      | Setup Required                                     |
| ---------------------------- | -------------------------------------------------- |
| **Email**                    | Connect email service (Mailgun, SMTP, or LC Email) |
| **SMS / MMS**                | LC Phone number or Twilio                          |
| **Phone Calls**              | LC Phone number                                    |
| **Facebook Messenger**       | Connect Facebook page                              |
| **Instagram DMs**            | Connect Instagram business account                 |
| **Google Business Messages** | Connect Google Business Profile                    |
| **WhatsApp**                 | WhatsApp Business API integration                  |
| **Live Chat**                | Add chat widget code to website                    |
| **TikTok DMs**               | Connect TikTok account (2025)                      |

### Inbox Best Practices

1. **Respond within 5 minutes** — Speed-to-lead is critical for conversion
2. **Use canned responses** — Pre-write responses for common questions
3. **Assign conversations** — Route to the right team member
4. **Mark as read/unread** — Keep inbox organized
5. **Use internal notes** — Coordinate with team members on a conversation
6. **Set up notifications** — Get alerted for new messages across all channels

---

## Email Marketing

### Email Service Options

| Provider        | Type             | Best For                                           |
| --------------- | ---------------- | -------------------------------------------------- |
| **LC Email**    | GHL native       | Simplest setup, built-in                           |
| **Mailgun**     | Third-party SMTP | Higher send volumes, better deliverability control |
| **Custom SMTP** | Self-managed     | Full control, existing infrastructure              |

### Email Configuration

1. **Connect email service** in Settings → Email Services
2. **Verify sending domain** — Add DNS records (SPF, DKIM, DMARC)
3. **Set default "From" address** — `yourname@yourdomain.com`
4. **Configure tracking** — Open tracking, click tracking, unsubscribe link

### Email Builder Features

- **Drag-and-drop editor** with pre-built blocks
- **HTML editor** for custom code
- **Merge fields** — `{{contact.first_name}}`, `{{contact.company}}`, etc.
- **Dynamic content** — Show/hide sections based on tags or custom fields
- **A/B testing** — Test subject lines, content, send times
- **Templates library** — Save and reuse email designs

### Email Campaign Best Practices

1. **Subject lines** — Keep under 50 characters; personalize with first name
2. **Preview text** — Add compelling preview text (shown in inbox next to subject)
3. **Mobile-first design** — 70%+ of emails are opened on mobile
4. **Single CTA** — One clear action per email
5. **Personalization** — Use merge fields and behavioral segmentation
6. **Send time** — Test optimal send times for your audience
7. **Clean your list** — Remove bounced, unsubscribed, and inactive contacts
8. **Warm up new domains** — Start with small volumes and increase gradually

### Deliverability Checklist

- [ ] SPF record configured
- [ ] DKIM record configured
- [ ] DMARC record configured
- [ ] Custom tracking domain set up
- [ ] Sending domain verified
- [ ] Unsubscribe link in every email
- [ ] Physical address in footer
- [ ] List hygiene (remove bounces regularly)
- [ ] Warm-up schedule for new domains (2-4 weeks)

---

## SMS Marketing

### Setup

1. **Get an LC Phone number** in Settings → Phone Numbers
2. **Register for A2P** (Application-to-Person) — Required for US businesses
3. **Verify your brand** through The Campaign Registry (TCR)
4. **Set up compliance** — Opt-in confirmation, opt-out handling

### SMS Best Practices

| Practice                 | Details                                       |
| ------------------------ | --------------------------------------------- |
| **Keep it short**        | Under 160 characters to avoid splitting       |
| **Personalize**          | Use `{{contact.first_name}}` in every message |
| **Include CTA**          | Every SMS should have a clear next step       |
| **Timing matters**       | Send between 9 AM–8 PM in contact's timezone  |
| **Use MMS sparingly**    | Images increase engagement but cost more      |
| **Respect frequency**    | Max 2-3 SMS per week per contact              |
| **Always offer opt-out** | Include "Reply STOP to unsubscribe"           |

### A2P Registration (US)

> **Required for all US-based SMS sending** — Without A2P registration, messages may be blocked by carriers.

1. **Brand Registration** — Register your business with The Campaign Registry
2. **Campaign Registration** — Register each use case (marketing, support, etc.)
3. **Approval** — Wait for carrier approval (2-15 business days)
4. **Monitor** — Track message delivery rates and carrier feedback

### SMS Compliance Rules

- **TCPA Compliance** — Written consent required before sending marketing SMS
- **Opt-in required** — Contacts must explicitly agree to receive messages
- **Opt-out honored immediately** — When someone texts STOP, cease all messages
- **Business hours** — Avoid sending before 8 AM or after 9 PM local time
- **Content restrictions** — No SHAFT content (Sex, Hate, Alcohol, Firearms, Tobacco)

---

## WhatsApp Integration

### Setup

1. Connect WhatsApp Business API through GHL settings
2. Verify your business phone number
3. Create message templates (pre-approved by WhatsApp)
4. Configure in Conversation AI or Workflow actions

### WhatsApp Features

- Template messages (marketing, utility, authentication)
- Free-form messaging within 24-hour conversation window
- Rich media (images, documents, videos)
- Interactive buttons and quick replies
- Integration with Conversation AI

---

## Multi-Channel Sequences

### Campaign Structure

```
Day 0: SMS — Immediate follow-up ("Thanks for reaching out!")
Day 0: Email — Welcome email with value proposition
Day 1: SMS — "Did you get a chance to review?"
Day 3: Email — Case study / testimonial
Day 5: SMS — Direct CTA with booking link
Day 7: Email — Final value-add content
Day 10: Voicemail Drop — Personal touch
Day 14: SMS — Last chance / special offer
```

### Channel Selection Guide

| Scenario                 | Best Channel     | Why                               |
| ------------------------ | ---------------- | --------------------------------- |
| **Immediate follow-up**  | SMS              | Highest open rates (98%)          |
| **Detailed content**     | Email            | Supports rich formatting          |
| **Appointment reminder** | SMS              | Read within 3 minutes             |
| **Nurture sequence**     | Email + SMS mix  | Email for content, SMS for nudges |
| **Re-engagement**        | SMS or Voicemail | Personal, attention-grabbing      |
| **Document delivery**    | Email            | Supports attachments              |

---

## Template Management

### Email Templates

- Create reusable email templates in Marketing → Emails → Templates
- Save designed emails as templates for workflow use
- Organize templates by category (welcome, follow-up, promotional, etc.)

### SMS Templates

- Save frequently used SMS messages as snippets
- Use custom values for business-specific content
- Create templates for each stage of the customer journey

### Template Naming Convention

```
[Channel] - [Purpose] - [Stage]
Examples:
  EMAIL - Welcome - New Lead
  SMS - Reminder - 24hr Before
  SMS - Follow-Up - Day 3
  EMAIL - Review Request - Post Service
```

---

## Key Metrics to Track

| Metric               | Email Target | SMS Target |
| -------------------- | ------------ | ---------- |
| **Open Rate**        | > 25%        | > 90%      |
| **Click Rate**       | > 3%         | > 10%      |
| **Reply Rate**       | > 5%         | > 15%      |
| **Unsubscribe Rate** | < 0.5%       | < 1%       |
| **Bounce Rate**      | < 2%         | < 5%       |
| **Conversion Rate**  | > 2%         | > 5%       |

---

## Key Resources

- **LC Email Setup**: Settings → Email Services
- **Phone Numbers**: Settings → Phone Numbers
- **A2P Registration**: Settings → Phone Numbers → Trust Center
- **Templates**: Marketing → Emails / SMS Templates
- **Compliance**: [TCPA Guidelines](https://www.fcc.gov/tcpa)
