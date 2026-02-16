---
name: GHL Reputation & Reviews
description: Guide for GoHighLevel reputation management — review request automation, Google/Facebook reviews, review widgets, response templates, and monitoring dashboards.
---

# GHL Reputation & Reviews

## Overview

GoHighLevel's reputation management tools help businesses automate review collection, monitor online reputation across platforms, and respond to reviews — all from within the platform.

---

## Core Features

| Feature                  | Description                                           |
| ------------------------ | ----------------------------------------------------- |
| **Review Requests**      | Automated SMS/email requests to customers for reviews |
| **Review Widget**        | Embeddable widget showing reviews on your website     |
| **Review Monitoring**    | Centralized dashboard for all platform reviews        |
| **Review Responses**     | Reply to reviews directly from GHL                    |
| **Review AI**            | AI-assisted review response generation                |
| **Reputation Dashboard** | Analytics on review volume, ratings, and trends       |

---

## Review Request Automation

### Workflow Setup

```
Trigger: Pipeline Stage → "Completed" / "Delivered"
→ Wait 1-2 days (let the experience settle)
→ Send SMS: Review request with direct link
→ Wait 3 days
→ If/Else: Review received?
   → Yes: Send thank-you message
   → No: Send Email: Gentle reminder
→ Wait 5 days
→ If no review: Final SMS reminder
→ Add tag: "review-requested"
```

### Review Request Message Templates

#### SMS Templates

**Initial Request:**

```
Hi {{contact.first_name}}! Thank you for choosing us! 🌟

We'd love your feedback. Could you take 30 seconds to leave a review?

{{custom_values.review_link}}

It means the world to us! Thank you!
```

**Reminder:**

```
Hey {{contact.first_name}}, just checking in! If you have a moment, we'd really appreciate a quick review:

{{custom_values.review_link}}

Thanks so much! 🙏
```

#### Email Templates

**Initial Request:**

```
Subject: How was your experience, {{contact.first_name}}?

Hi {{contact.first_name}},

Thank you for choosing {{custom_values.business_name}}!

We hope we exceeded your expectations. Your feedback helps us
improve and helps others find us.

Would you mind leaving a brief review? It only takes 30 seconds:

[Leave a Review ▸]({{custom_values.review_link}})

Thank you for your time and trust!

— The {{custom_values.business_name}} Team
```

---

## Review Link Strategy

### Two-Step vs. Direct Link

**Two-Step Funnel (Recommended):**

```
Review Request → GHL Landing Page
   → "How was your experience?" (5-star scale)
      → 4-5 stars → Redirect to Google/Facebook review page
      → 1-3 stars → Redirect to private feedback form
```

**Benefits:**

- Filters negative reviews to private channel
- Captures positive reviews on public platforms
- Provides opportunity to resolve issues privately

**Direct Link:**

- Send directly to Google or Facebook review page
- Simpler but no negative review filtering

### Setting Up Review Links

| Platform     | Link Format                                                           |
| ------------ | --------------------------------------------------------------------- |
| **Google**   | `https://search.google.com/local/writereview?placeid={YOUR_PLACE_ID}` |
| **Facebook** | `https://facebook.com/{YOUR_PAGE}/reviews`                            |
| **Yelp**     | `https://www.yelp.com/writeareview/biz/{YOUR_BIZ_ID}`                 |

> Store review links as **Custom Values** (e.g., `{{custom_values.google_review_link}}`) for easy updating.

---

## Review Widget

### Setup

1. Go to **Reputation → Widget Settings**
2. Customize appearance:
   - Widget style (grid, slider, list)
   - Colors to match your brand
   - Number of reviews shown
   - Minimum star rating to display
3. Copy the embed code
4. Add to your website or funnel pages

### Widget Best Practices

1. **Place on high-traffic pages** — Homepage, services page, contact page
2. **Show recent reviews** — Keep content fresh and relevant
3. **Filter by rating** — Only display 4-5 star reviews
4. **Include reviewer names** — Adds authenticity (with permission)
5. **Keep it loading fast** — Don't overload with too many reviews

---

## Review Monitoring

### Dashboard Metrics

| Metric                    | What to Track                         |
| ------------------------- | ------------------------------------- |
| **Overall Rating**        | Average star rating across platforms  |
| **Review Volume**         | Number of reviews per week/month      |
| **Response Rate**         | % of reviews you've responded to      |
| **Sentiment Trend**       | Are ratings improving or declining?   |
| **Platform Distribution** | Which platforms have the most reviews |

### Monitoring Best Practices

1. **Check daily** — Respond to all reviews within 24 hours
2. **Set up alerts** — Get notified for new reviews immediately
3. **Track competitors** — Monitor competitor review activity
4. **Report monthly** — Share reputation reports with stakeholders

---

## Responding to Reviews

### Positive Review Response Template

```
Thank you so much, [Name]! We're thrilled to hear about your
experience. It was a pleasure working with you, and we look
forward to seeing you again! ⭐
```

### Negative Review Response Template

```
Hi [Name], thank you for taking the time to share your feedback.
We're sorry to hear about your experience and would love the
opportunity to make it right. Please reach out to us directly
at [phone/email] so we can address your concerns.
```

### Response Best Practices

1. **Respond to ALL reviews** — Both positive and negative
2. **Be timely** — Within 24 hours for positive, within 2 hours for negative
3. **Be professional** — Never argue or be defensive
4. **Personalize** — Reference specific details from the review
5. **Take it offline** — For negative reviews, move the conversation to private
6. **Use AI assistance** — Review AI can draft responses you then customize
7. **Thank reviewers** — Always express gratitude

---

## Review AI

GHL's Review AI automates response drafting:

1. **Enable** in Reputation settings
2. **Configure tone** — Professional, friendly, casual
3. **Set auto-response rules** — Auto-respond to 5-star reviews
4. **Review before sending** — Always check AI-generated responses for accuracy
5. **Customize templates** — Train the AI with your preferred response style

---

## Reputation KPIs by Industry

| Industry          | Target Rating | Monthly Reviews | Response Rate |
| ----------------- | ------------- | --------------- | ------------- |
| **Dental**        | ≥ 4.7         | 10-20           | 100%          |
| **Real Estate**   | ≥ 4.8         | 5-10            | 100%          |
| **Home Services** | ≥ 4.5         | 15-30           | 95%+          |
| **Restaurants**   | ≥ 4.3         | 20-50           | 90%+          |
| **Legal**         | ≥ 4.8         | 5-10            | 100%          |
| **Fitness**       | ≥ 4.6         | 10-20           | 95%+          |

---

## Key Resources

- **Reputation Dashboard**: Reputation tab in sub-account
- **Review Widget**: Reputation → Widget Settings
- **Google Business Profile**: [business.google.com](https://business.google.com)
- **Help Docs**: [GoHighLevel Reputation Guide](https://help.gohighlevel.com)
