---
name: GHL API v2 & Integrations
description: Developer reference for GoHighLevel API v2 — OAuth 2.0, private tokens, endpoint reference, rate limits, webhooks, and building marketplace apps.
---

# GHL API v2 & Integrations

## Overview

GoHighLevel's API v2 is a RESTful API providing programmatic access to the platform's features. It enables custom integrations, workflow automation, data syncing, and building marketplace applications.

> **Important**: API v1 is deprecated. All new development should use API v2.

- **Base URL**: `https://services.leadconnectorhq.com`
- **Docs**: [https://marketplace.gohighlevel.com/docs/](https://marketplace.gohighlevel.com/docs/)
- **GitHub**: [https://github.com/GoHighLevel/highlevel-api-docs](https://github.com/GoHighLevel/highlevel-api-docs)

---

## Authentication

### OAuth 2.0 (Authorization Code Grant)

Used for **Marketplace Apps** and multi-location integrations.

**Flow:**

```
1. User clicks "Install" on your marketplace app
2. Redirect to GHL authorization URL
3. User grants permission
4. Receive authorization code
5. Exchange code for access_token + refresh_token
6. Use access_token in API calls
7. Refresh token before expiry
```

**Authorization URL:**

```
https://marketplace.gohighlevel.com/oauth/chooselocation
  ?response_type=code
  &redirect_uri={YOUR_REDIRECT_URI}
  &client_id={YOUR_CLIENT_ID}
  &scope={SCOPES}
```

**Token Exchange:**

```http
POST https://services.leadconnectorhq.com/oauth/token
Content-Type: application/x-www-form-urlencoded

client_id={CLIENT_ID}
&client_secret={CLIENT_SECRET}
&grant_type=authorization_code
&code={AUTH_CODE}
&redirect_uri={REDIRECT_URI}
```

**Token Refresh:**

```http
POST https://services.leadconnectorhq.com/oauth/token
Content-Type: application/x-www-form-urlencoded

client_id={CLIENT_ID}
&client_secret={CLIENT_SECRET}
&grant_type=refresh_token
&refresh_token={REFRESH_TOKEN}
```

### Private Integration Token

Used for **single-location** or internal integrations (no OAuth flow needed).

1. Go to **Settings → Integrations → Private Integrations** in your sub-account
2. Create a new integration
3. Select required scopes
4. Copy the generated API key

**Usage:**

```http
GET https://services.leadconnectorhq.com/contacts/
Authorization: Bearer {PRIVATE_TOKEN}
Version: 2021-07-28
```

---

## Rate Limits

| Limit Type | Value                                                   |
| ---------- | ------------------------------------------------------- |
| **Burst**  | 100 requests per 10 seconds                             |
| **Daily**  | 200,000 requests per day                                |
| **Scope**  | Per marketplace app, per resource (Location or Company) |

**Rate limit headers** are returned in API responses:

```
X-RateLimit-Limit: 100
X-RateLimit-Remaining: 87
X-RateLimit-Reset: 1639159200
```

> **Best Practice**: Implement exponential backoff when receiving `429 Too Many Requests`.

---

## API Endpoint Reference

### Contacts

| Method   | Endpoint                      | Description          |
| -------- | ----------------------------- | -------------------- |
| `GET`    | `/contacts/{contactId}`       | Get a contact by ID  |
| `GET`    | `/contacts/`                  | Search/list contacts |
| `POST`   | `/contacts/`                  | Create a new contact |
| `PUT`    | `/contacts/{contactId}`       | Update a contact     |
| `DELETE` | `/contacts/{contactId}`       | Delete a contact     |
| `POST`   | `/contacts/{contactId}/tags`  | Add tags             |
| `DELETE` | `/contacts/{contactId}/tags`  | Remove tags          |
| `GET`    | `/contacts/{contactId}/tasks` | Get contact tasks    |
| `GET`    | `/contacts/{contactId}/notes` | Get contact notes    |

### Conversations

| Method | Endpoint                                          | Description                  |
| ------ | ------------------------------------------------- | ---------------------------- |
| `GET`  | `/conversations/{conversationId}`                 | Get conversation             |
| `GET`  | `/conversations/search`                           | Search conversations         |
| `POST` | `/conversations/messages`                         | Send a message               |
| `GET`  | `/conversations/{id}/messages`                    | Get messages in conversation |
| `PUT`  | `/conversations/{id}/messages/{messageId}/status` | Update message status        |

### Calendars & Appointments

| Method | Endpoint                             | Description         |
| ------ | ------------------------------------ | ------------------- |
| `GET`  | `/calendars/`                        | List calendars      |
| `GET`  | `/calendars/{calendarId}`            | Get calendar        |
| `POST` | `/calendars/`                        | Create calendar     |
| `PUT`  | `/calendars/{calendarId}`            | Update calendar     |
| `GET`  | `/calendars/{calendarId}/free-slots` | Get available slots |
| `GET`  | `/calendars/events`                  | List appointments   |
| `POST` | `/calendars/events`                  | Book appointment    |
| `PUT`  | `/calendars/events/{eventId}`        | Update appointment  |

### Opportunities

| Method   | Endpoint                     | Description                   |
| -------- | ---------------------------- | ----------------------------- |
| `GET`    | `/opportunities/search`      | Search opportunities          |
| `GET`    | `/opportunities/{id}`        | Get opportunity               |
| `POST`   | `/opportunities/`            | Create opportunity            |
| `PUT`    | `/opportunities/{id}`        | Update opportunity            |
| `DELETE` | `/opportunities/{id}`        | Delete opportunity            |
| `PUT`    | `/opportunities/{id}/status` | Update status (won/lost/open) |
| `GET`    | `/opportunities/pipelines`   | List pipelines                |

### Payments

| Method | Endpoint                     | Description                    |
| ------ | ---------------------------- | ------------------------------ |
| `GET`  | `/payments/orders`           | List orders                    |
| `GET`  | `/payments/orders/{orderId}` | Get order details              |
| `GET`  | `/payments/subscriptions`    | List subscriptions             |
| `GET`  | `/payments/transactions`     | List transactions              |
| `POST` | `/payments/custom-provider/` | Create custom payment provider |

### Workflows

| Method   | Endpoint                                      | Description                  |
| -------- | --------------------------------------------- | ---------------------------- |
| `GET`    | `/workflows/`                                 | List workflows               |
| `POST`   | `/contacts/{contactId}/workflow/{workflowId}` | Add contact to workflow      |
| `DELETE` | `/contacts/{contactId}/workflow/{workflowId}` | Remove contact from workflow |

### Other Endpoints

- **Users**: CRUD for agency/location users
- **Locations**: Manage sub-accounts
- **Forms**: List and retrieve form submissions
- **Surveys**: List and retrieve survey submissions
- **Businesses**: Manage business profiles
- **Social Planner**: Schedule and manage social posts
- **Media**: Upload and manage files
- **Custom Fields / Custom Values**: CRUD operations

---

## Webhooks

Webhooks push real-time event data to your application.

### Setup

1. Go to **Settings → Integrations → Webhooks** in your sub-account
2. Add a webhook URL
3. Select events to subscribe to

### Key Webhook Events

| Event                      | Description                       |
| -------------------------- | --------------------------------- |
| `ContactCreate`            | New contact created               |
| `ContactUpdate`            | Contact record updated            |
| `ContactDelete`            | Contact deleted                   |
| `ContactTagUpdate`         | Tag added or removed              |
| `ConversationUnreadUpdate` | New unread message                |
| `InboundMessage`           | Incoming SMS, email, or chat      |
| `OutboundMessage`          | Outgoing message sent             |
| `AppointmentCreate`        | New appointment booked            |
| `AppointmentUpdate`        | Appointment rescheduled/cancelled |
| `OpportunityCreate`        | New opportunity created           |
| `OpportunityStageUpdate`   | Opportunity moved to new stage    |
| `OpportunityStatusUpdate`  | Opportunity won/lost/abandoned    |
| `TaskCreate`               | New task assigned                 |
| `NoteCreate`               | New note added                    |
| `FormSubmission`           | Form submitted                    |
| `SurveySubmission`         | Survey completed                  |

### Webhook Payload Example

```json
{
  "type": "ContactCreate",
  "locationId": "loc_abc123",
  "id": "contact_xyz789",
  "firstName": "John",
  "lastName": "Doe",
  "email": "john@example.com",
  "phone": "+15551234567",
  "tags": ["new-lead", "source:facebook"],
  "dateAdded": "2025-01-15T10:30:00Z"
}
```

### Best Practices

1. **Respond with 200 quickly** — Process webhook data asynchronously
2. **Validate payloads** — Check for required fields before processing
3. **Handle duplicates** — Implement idempotency for webhook handlers
4. **Log everything** — Store raw payloads for debugging
5. **Set up retry logic** — GHL retries failed webhook deliveries

---

## Building Marketplace Apps

### Steps

1. **Create a developer account** at [marketplace.gohighlevel.com](https://marketplace.gohighlevel.com)
2. **Register your app** — Set redirect URIs, scopes, and app details
3. **Implement OAuth 2.0** — Handle auth flow, token storage, and refresh
4. **Build your integration** — Use API endpoints to interact with GHL data
5. **Submit for review** — GHL reviews before publishing to the marketplace
6. **Maintain and update** — Monitor for API changes and update accordingly

### Required Scopes

Select only the scopes your app needs:

- `contacts.readonly` / `contacts.write`
- `conversations.readonly` / `conversations.write` / `conversations/message.readonly` / `conversations/message.write`
- `calendars.readonly` / `calendars.write` / `calendars/events.readonly` / `calendars/events.write`
- `opportunities.readonly` / `opportunities.write`
- `locations.readonly` / `locations.write`
- `workflows.readonly`
- `users.readonly` / `users.write`
- `payments.readonly` / `payments.write`
- `forms.readonly` / `surveys.readonly`

---

## Integration Patterns

### Common Integrations

| Tool                  | Pattern                                   |
| --------------------- | ----------------------------------------- |
| **Zapier**            | Use GHL's Zapier app or custom webhooks   |
| **Make (Integromat)** | HTTP module with API endpoints            |
| **Google Sheets**     | Native workflow action or API-based sync  |
| **Slack**             | Webhook notifications from workflows      |
| **Stripe**            | Native integration for payments           |
| **WordPress**         | Embed forms, calendars; use tracking code |
| **Shopify**           | Webhook-based order sync                  |
| **Custom Apps**       | Direct API v2 integration                 |

### Data Sync Pattern

```
External System ←→ Middleware (Node.js/Python) ←→ GHL API v2
                                                    ↕
                                              GHL Webhooks
```

### Error Handling

```javascript
// Example: Node.js API call with error handling
async function getContact(contactId, token) {
  try {
    const response = await fetch(
      `https://services.leadconnectorhq.com/contacts/${contactId}`,
      {
        headers: {
          Authorization: `Bearer ${token}`,
          Version: "2021-07-28",
        },
      },
    );

    if (response.status === 429) {
      // Rate limited — wait and retry
      const retryAfter = response.headers.get("Retry-After") || 10;
      await sleep(retryAfter * 1000);
      return getContact(contactId, token); // Retry
    }

    if (!response.ok) {
      throw new Error(`API Error: ${response.status} ${response.statusText}`);
    }

    return await response.json();
  } catch (error) {
    console.error("GHL API Error:", error);
    throw error;
  }
}
```

---

## Key Resources

- **API Docs**: [marketplace.gohighlevel.com/docs](https://marketplace.gohighlevel.com/docs/)
- **GitHub**: [GoHighLevel/highlevel-api-docs](https://github.com/GoHighLevel/highlevel-api-docs)
- **Postman Collection**: Available in the official GitHub repo
- **Developer Community**: [GHL Developer Facebook Group](https://www.facebook.com/groups/gohighlevel)
