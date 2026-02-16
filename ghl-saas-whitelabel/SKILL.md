---
name: GHL SaaS Mode & White-Label
description: Agency setup guide for GoHighLevel SaaS mode — white-labeling, Stripe integration, custom domains, pricing plans, snapshots, and client onboarding.
---

# GHL SaaS Mode & White-Label

## Overview

GoHighLevel's SaaS Mode enables agencies to rebrand the platform as their own software product, creating a recurring revenue business by selling access to clients. This covers white-labeling, billing, snapshots, and client management.

---

## Plans & Pricing Tiers

| Plan           | Monthly Cost | Key SaaS Features                                   |
| -------------- | ------------ | --------------------------------------------------- |
| **Starter**    | $97/mo       | Single sub-account, no SaaS mode                    |
| **Unlimited**  | $297/mo      | Unlimited sub-accounts, basic white-label           |
| **Agency Pro** | $497/mo      | Full SaaS mode, advanced white-labeling, API access |

> **SaaS Mode requires the Agency Pro plan** for full capabilities including automated billing, custom domains, and app branding.

---

## White-Label Setup

### Step-by-Step

1. **Custom Domain**
   - Set up a branded login URL (e.g., `app.youragency.com`)
   - Add a CNAME record pointing to GHL's servers
   - SSL is automatically provisioned

2. **Branding**
   - Upload your agency logo (light and dark versions)
   - Set brand colors for the platform UI
   - Add a favicon
   - Customize the login page design

3. **Email Branding**
   - Configure custom email domain (e.g., `noreply@yourbrand.com`)
   - Set up SPF, DKIM, and DMARC records for deliverability
   - Customize system email templates

4. **Mobile App Branding** (Agency Pro)
   - Custom app name on iOS/Android stores
   - Custom app icon and splash screen
   - Branded push notifications

5. **Desktop App**
   - Mac desktop app available (2025)
   - Windows version expected (2026)
   - Branded workspace experience

---

## Stripe Integration & Billing

### Setup

1. Connect your Stripe account in **Agency Settings → Billing**
2. GHL handles subscription management automatically
3. Payments flow directly to your Stripe account

### Creating Pricing Plans

| Element            | Description                               |
| ------------------ | ----------------------------------------- |
| **Plan Name**      | Client-facing name (e.g., "Growth Plan")  |
| **Price**          | Monthly or annual recurring fee           |
| **Trial Period**   | Free trial duration (optional)            |
| **Setup Fee**      | One-time onboarding charge (optional)     |
| **Feature Limits** | Contacts, users, SMS credits, email sends |
| **Snapshot**       | Auto-load a snapshot template on signup   |

### Pricing Strategy Best Practices

1. **Offer 3 tiers** — Starter / Growth / Pro (or similar)
2. **Anchor pricing** — Make the middle tier most attractive
3. **Include setup fees** — Offset initial onboarding cost
4. **Add usage-based upsells** — SMS credits, AI minutes, phone numbers
5. **Annual discounts** — Offer 10-20% off for yearly commitments
6. **Free trials** — 14-day trials increase conversion rates

### Example Pricing Structure

```
┌──────────────┬──────────────┬──────────────┐
│   STARTER    │    GROWTH    │     PRO      │
│   $97/mo     │   $197/mo    │   $297/mo    │
├──────────────┼──────────────┼──────────────┤
│ 500 contacts │ 2,500 contacts│ Unlimited   │
│ 1 user       │ 3 users      │ 10 users     │
│ 1 pipeline   │ 3 pipelines  │ Unlimited    │
│ Basic funnel │ 5 funnels    │ Unlimited    │
│ Email only   │ Email + SMS  │ All channels │
│ —            │ Basic AI     │ Full AI      │
│ —            │ —            │ API access   │
└──────────────┴──────────────┴──────────────┘
```

---

## Snapshots

### What Are Snapshots?

Pre-configured sub-account templates that bundle:

- Funnels and landing pages
- Workflows and automations
- Email/SMS templates
- Calendar configurations
- Pipelines with stages
- Custom fields and tags
- Forms and surveys
- Custom values

### Creating Effective Snapshots

1. **Build in a dedicated sub-account** — Keep snapshot-building separate from live accounts
2. **Use generic content** — Avoid client-specific details; use custom values as placeholders
3. **Name everything clearly** — Descriptive names for all funnels, workflows, tags
4. **Test thoroughly** — Run through every workflow, form, and funnel before snapshotting
5. **Document the snapshot** — Create a setup guide showing what's included and what needs customization

### Snapshot Best Practices

| Practice                           | Reason                                            |
| ---------------------------------- | ------------------------------------------------- |
| **Build niche-specific snapshots** | Industry-tailored setups convert better           |
| **Keep modular**                   | Smaller, focused snapshots are easier to maintain |
| **Include onboarding workflow**    | Auto-welcome new clients with training            |
| **Add sample data**                | Demo contacts and deals for illustration          |
| **Use custom values everywhere**   | Enable easy per-client customization              |
| **Update regularly**               | Refresh with new features and best practices      |

### Essential Snapshot Components

For any niche, include these:

- [ ] Lead capture funnel (landing page + thank you page)
- [ ] Speed-to-lead workflow (immediate follow-up)
- [ ] Appointment booking calendar
- [ ] Appointment reminder sequence
- [ ] Pipeline with 5-7 stages
- [ ] Review request automation
- [ ] Nurture email/SMS sequence (5-7 messages)
- [ ] Reactivation campaign for cold leads
- [ ] Internal notification workflows
- [ ] Custom fields for niche-specific data
- [ ] Custom values for business info placeholders

### Linking Snapshots to SaaS Plans

1. Go to **Agency Settings → SaaS Configurator**
2. Select a pricing plan
3. Assign a snapshot to that plan
4. When a client signs up, the snapshot auto-deploys to their sub-account

---

## Client Onboarding

### Automated Onboarding Flow

```
Client Signs Up
  → Stripe charges first payment
  → Sub-account auto-created
  → Snapshot auto-deployed
  → Welcome email sent (with login credentials)
  → Onboarding workflow triggers
  → Training materials delivered over 7 days
  → Check-in task created for agency team
```

### Onboarding Best Practices

1. **Automate everything possible** — Reduce manual setup to minutes
2. **Provide video tutorials** — Record Loom walkthroughs for each feature
3. **Assign a success manager** — A human point of contact for questions
4. **Milestone notifications** — Alert clients as they complete setup steps
5. **30-day check-in** — Follow up to ensure adoption and satisfaction

---

## Sub-Account Management

### Organization

1. **Naming convention** — `[Client Name] - [Industry]` for easy identification
2. **Tag accounts** — Categorize by plan tier, industry, or status
3. **Regular audits** — Review inactive accounts monthly
4. **Usage monitoring** — Track contact counts, message volumes, and AI usage per account

### Key Metrics to Track

| Metric                              | Target                    |
| ----------------------------------- | ------------------------- |
| **Monthly Recurring Revenue (MRR)** | Growing month-over-month  |
| **Client Churn Rate**               | < 5% monthly              |
| **Time to First Value**             | < 7 days from signup      |
| **Support Ticket Volume**           | Decreasing over time      |
| **Feature Adoption Rate**           | > 60% using core features |

---

## Key Resources

- **SaaS Configurator**: Settings → SaaS in agency dashboard
- **Snapshot Templates**: [GHL Marketplace](https://marketplace.gohighlevel.com)
- **White-Label Guide**: [GHL Help Center](https://help.gohighlevel.com)
