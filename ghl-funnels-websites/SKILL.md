---
name: GHL Funnels & Website Builder
description: Complete guide for GoHighLevel funnel builder, landing pages, and website creation — design principles, conversion optimization, mobile responsiveness, SEO, and A/B testing.
---

# GHL Funnels & Website Builder

## Overview

GoHighLevel provides a drag-and-drop builder for funnels (multi-step sequences), landing pages (single pages), and full websites. These tools integrate directly with the CRM, forms, calendars, and payment systems.

---

## Key Concepts

| Concept           | Description                                                                                    |
| ----------------- | ---------------------------------------------------------------------------------------------- |
| **Funnel**        | A multi-step sequence guiding visitors toward a conversion (lead capture → thank you → upsell) |
| **Landing Page**  | A single, focused page designed for one specific CTA                                           |
| **Website**       | A full multi-page site with navigation, built inside GHL                                       |
| **Funnel Step**   | An individual page within a funnel                                                             |
| **Row / Section** | Horizontal containers that organize page content                                               |
| **Column**        | Vertical divisions within a row                                                                |
| **Element**       | Individual content blocks (text, image, button, form, video, etc.)                             |

---

## Funnel Builder

### Funnel Architecture Best Practices

1. **Map the customer path** before building:

   ```
   Ad / Email → Landing Page → Form / Calendar → Thank You Page → Follow-Up Workflow
   ```

2. **Keep funnels simple** — 2-4 steps is optimal for most use cases
3. **One CTA per page** — Each step should have a single, clear action
4. **Use templates** — Start from GHL marketplace templates, then customize

### Funnel Types

| Type            | Steps                                     | Use Case                                    |
| --------------- | ----------------------------------------- | ------------------------------------------- |
| **Lead Magnet** | Opt-in → Thank You                        | Email list building, free resource delivery |
| **Webinar**     | Registration → Confirmation → Replay      | Education-based selling                     |
| **Sales Page**  | Long-form page → Checkout → Thank You     | Direct product/service sales                |
| **Application** | Landing → Application Form → Confirmation | High-ticket qualification                   |
| **Appointment** | Landing → Calendar Booking → Confirmation | Service-based bookings                      |
| **Survey**      | Survey → Qualify → Offer                  | Lead qualification funnels                  |

### Conversion Optimization

1. **Optimize the first screen ("above the fold")**
   - Clear promise/headline
   - Single CTA button
   - Minimal visual clutter
   - Short proof point near the button

2. **Shorten forms** — Ask only essential info (name + email minimum)
   - Only request phone number if a call is the immediate next step
   - Use multi-step forms to reduce perceived length

3. **Place calendars strategically** — If booking is the goal, make it front and center

4. **Add social proof** — Testimonials, review counts, trust badges, client logos

5. **Create urgency** — Countdown timers, limited spots, deadline messaging

6. **A/B test** — Use GHL's split testing to compare headlines, CTAs, page layouts

---

## Landing Page Design

### Design Principles

1. **Visual hierarchy** — Arrange elements by importance (heading → subtext → CTA → proof)
2. **Consistent branding** — Use your brand colors, fonts, and imagery throughout
3. **Whitespace** — Don't overcrowd; give elements room to breathe
4. **Typography** — Use the Typography tab for global font settings; max 2 font families
5. **Color contrast** — CTA buttons should contrast strongly with the background
6. **Image optimization** — Compress images (TinyPNG, Squoosh) for fast load times

### Page Structure Template

```
┌─────────────────────────────────────┐
│           HERO SECTION              │
│  Headline + Subheadline + CTA      │
│  (Optional: Hero image/video)      │
├─────────────────────────────────────┤
│         SOCIAL PROOF BAR           │
│  "Trusted by 500+ businesses"      │
│  Client logos / review stars        │
├─────────────────────────────────────┤
│         BENEFITS SECTION           │
│  3 columns with icon + text         │
├─────────────────────────────────────┤
│         HOW IT WORKS               │
│  Step 1 → Step 2 → Step 3          │
├─────────────────────────────────────┤
│         TESTIMONIALS               │
│  Cards with photo + quote + name    │
├─────────────────────────────────────┤
│         CTA SECTION                │
│  Final call to action + button      │
├─────────────────────────────────────┤
│           FOOTER                    │
│  Links, contact info, legal         │
└─────────────────────────────────────┘
```

### Mobile Responsiveness

> **Critical**: A significant portion of traffic comes from mobile devices. Always check mobile view.

1. **Switch to mobile view** in the editor and adjust independently
2. **Reduce font sizes** for mobile (typically 80% of desktop)
3. **Stack columns vertically** on mobile
4. **Hide non-essential sections** on mobile using visibility settings
5. **Ensure buttons are thumb-friendly** — Minimum 44px height
6. **Test on actual devices** — Don't rely solely on the editor preview

---

## Website Builder

### Setup Checklist

- [ ] Choose and customize a template
- [ ] Connect your custom domain
- [ ] Enable SSL/HTTPS
- [ ] Set up navigation menu
- [ ] Configure SEO settings for each page
- [ ] Add Google Analytics / tracking pixels
- [ ] Set up favicon and social share images
- [ ] Build mobile-responsive layouts
- [ ] Create a 404 error page
- [ ] Submit XML sitemap to Google Search Console

### Website vs. Funnel

| Feature        | Website                          | Funnel                     |
| -------------- | -------------------------------- | -------------------------- |
| **Navigation** | Full site nav menu               | Typically no nav (focused) |
| **Pages**      | Multiple interconnected pages    | Sequential step-by-step    |
| **Purpose**    | Brand presence, information, SEO | Conversion, lead capture   |
| **SEO**        | Fully optimized for search       | Usually for paid traffic   |
| **Best For**   | Businesses needing a full site   | Specific campaigns/offers  |

---

## SEO Configuration

### Per-Page Settings

1. **SEO Title** — Include primary keyword, 50-60 characters
2. **Meta Description** — Compelling summary, 150-160 characters
3. **URL Slug** — Clean, keyword-rich (e.g., `/free-consultation`)
4. **Image Alt Tags** — Descriptive text on all images
5. **Heading Structure** — One `H1` per page, logical `H2`/`H3` hierarchy

### Site-Wide Settings

1. **Auto-generate sitemap** — Enable in domain settings
2. **Block pages from indexing** — Mark thank-you or internal pages as `noindex`
3. **Custom domain** — Use your own domain (not the GHL subdomain)
4. **Page speed** — Compress images, minimize custom code, avoid heavy scripts

---

## Forms & Checkout

### Form Best Practices

1. **Minimize fields** — Name, email, and one qualifying question
2. **Use drop-downs** for structured data (service type, budget range)
3. **Add hidden fields** — Pass UTM parameters, source, and campaign data
4. **Styled consistently** — Match form styling to the page design
5. **Thank you action** — Redirect to a thank-you page or show an inline message

### Payment/Checkout

1. **Connect Stripe** — Set up payment integration in sub-account settings
2. **Create order forms** — Add product, pricing, and checkout flow
3. **Offer payment plans** — Split payments for high-ticket items
4. **Add order bumps** — Low-cost add-ons at checkout
5. **Set up one-click upsells** — Post-purchase offer pages

---

## Element Library

Available drag-and-drop elements in the builder:

| Category     | Elements                                                             |
| ------------ | -------------------------------------------------------------------- |
| **Layout**   | Row, Column, Section Divider                                         |
| **Text**     | Headline, Sub-headline, Paragraph, Bullet List                       |
| **Media**    | Image, Video, Image Carousel, Background Video                       |
| **Forms**    | Form Builder, Survey, Custom Field Forms                             |
| **Buttons**  | Button, Floating Button                                              |
| **Booking**  | Calendar Widget, Booking Embed                                       |
| **Payments** | Order Form, Price Table                                              |
| **Social**   | Social Icons, Testimonial Cards                                      |
| **Advanced** | Custom HTML/CSS, Countdown Timer, Progress Bar, FAQ Accordion, Popup |
| **Tracking** | Facebook Pixel, Google Tag, Custom Scripts                           |

---

## Common Mistakes to Avoid

1. ❌ Not testing mobile view before publishing
2. ❌ Using too many fonts or colors
3. ❌ Placing multiple CTAs that compete with each other
4. ❌ Heavy custom CSS that breaks responsiveness
5. ❌ Missing SEO meta data on published pages
6. ❌ Not connecting forms to workflows
7. ❌ Using GHL subdomain instead of a custom domain
8. ❌ Forgetting to test all links and redirects

---

## Key Resources

- **Templates**: [GHL Marketplace Templates](https://marketplace.gohighlevel.com)
- **Image Compression**: [TinyPNG](https://tinypng.com), [Squoosh](https://squoosh.app)
- **Official Help**: [GoHighLevel Help Center](https://help.gohighlevel.com)
