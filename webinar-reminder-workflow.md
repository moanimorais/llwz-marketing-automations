[webinar-reminder-workflow.md](https://github.com/user-attachments/files/27212188/webinar-reminder-workflow.md)
# Webinar Reminder Workflow

Automated email reminder system for menopause webinars.  
Sends two timed reminders to registered attendees:

- **1 day before** the webinar at 10:00 AM EST
- **1 hour before** the webinar at 2:00 PM EST

**Stack:** Eventbrite → Zapier → GoHighLevel (LeadConnector)

---

## Architecture

```
Eventbrite (New Attendee Registered)
        ↓
Zapier — Add/Update Contact in GHL
  Tags: "thriving through menopause" + "webinar_may_23"
        ↓
GHL Workflow — triggered by tag "thriving through menopause"
        ↓
IF/Branch — identifies which webinar the contact registered for
        ↓
Update Contact Field — sets Zoom Access Details for that date
        ↓
Wait 1 — Friday at 10:00 AM EST (1 day before)
        ↓
Email 1 — "See you tomorrow"
        ↓
Wait 2 — Saturday at 2:00 PM EST (day of event)
        ↓
Email 2 — "Starting in 1 hour"
        ↓
END
```

---

## Zapier Setup

**Zap name:** `[AIOM - email workflow] - Menopause Webinar - May 23`

| Step | App | Action | Details |
|------|-----|--------|---------|
| 1 | Eventbrite | New Attendee Registered | Organization: Live Life with Zest |
| 2 | LeadConnector | Add/Update Contact | Maps: first name, last name, phone, email |

**Tags added on Step 2:**

```
Thriving through Menopause, webinar_may_23, status_new_lead
```

> ⚠️ Each webinar date requires its own Zap with a unique date tag.  
> Example: `webinar_jun_13`, `webinar_jul_25`, etc.

---

## GHL Workflow Setup

### Trigger

| Setting | Value |
|---------|-------|
| Type | Contact Tag |
| Filter | Tag Added = `thriving through menopause` |

---

### Branch Logic

One branch per webinar date. Each branch checks for its corresponding tag:

| Branch | Condition | Action |
|--------|-----------|--------|
| Branch — May 23 | Tags includes `webinar_may_23` | Update Zoom link for May 23 |
| Branch 1 — Jun 13 | Tags includes `webinar_jun_13` | Update Zoom link for Jun 13 |
| Branch 2 — Jul 25 | Tags includes `webinar_jul_25` | Update Zoom link for Jul 25 |
| Branch 3 — Aug 15 | Tags includes `webinar_aug_15` | Update Zoom link for Aug 15 |
| Branch 4 — Sep 26 | Tags includes `webinar_sep_26` | Update Zoom link for Sep 26 |

---

### Update Contact Field

| Setting | Value |
|---------|-------|
| Field | `Zoom Access Details` |
| Value | Full Zoom join link for the specific webinar |

> This populates `{{contact.zoom_access_details}}` used in both reminder emails.

---

### Wait 1 — Day Before Reminder

| Setting | Value |
|---------|-------|
| Type | Time Delay |
| Wait | 1 day |
| Advance Window | ON |
| Resume On | Friday |
| Resume Between Hours | Exact |
| Resume At | 10:00 AM |

> All webinars fall on **Saturdays**, so the day before is always **Friday**.

---

### Email 1 — See You Tomorrow

**Subject:**
```
Tomorrow is the day, {{contact.first_name}}! 🗓️
```

**Body:**
```
Hi {{contact.first_name}},

You did it. You officially said YES to yourself. We love that for you. 🙌

Here are your details for the 3 Truths Every Woman Needs to Know 
to Thrive in Menopause:

📅 TOMORROW! [Date], 3:00 PM (EST)
🔗 Zoom Link: {{contact.zoom_access_details}}

While you count down the hours (don't pretend you're not), why not 
meet the women who will become your people?

The Zest Collective is our community of women who are done suffering 
in silence and started thriving out loud. 💃

👉 Join The Zest Collective: https://www.livelifewithzest.com/the-zest-collective

See you soon!
Madelaine
Live Life with Zest
```

---

### Wait 2 — Day Of Reminder

| Setting | Value |
|---------|-------|
| Type | Time Delay |
| Wait | 1 day |
| Advance Window | ON |
| Resume On | Saturday |
| Resume Between Hours | Exact |
| Resume At | 2:00 PM |

---

### Email 2 — Starting in 1 Hour

**Subject:**
```
You're on in 1 hour, {{contact.first_name}}! ⏰
```

**Body:**
```
Hi {{contact.first_name}},

This is your 1-hour warning — and yes, we're excited for you. 🙌

Your 3 Truths Every Woman Needs to Know to Thrive in Menopause 
session starts at 3:00 PM EST today.

👉 {{contact.zoom_access_details}}

Grab your coffee, find a quiet spot, and show up for yourself — 
you already did the hard part by signing up. 💃

See you at 3!
Madelaine
Live Life with Zest
```

---

## Webinar Dates & Tags Reference

| Webinar Date | Day | Tag | Wait 1 | Wait 2 |
|---|---|---|---|---|
| May 23, 2026 | Saturday | `webinar_may_23` | Fri 10:00 AM | Sat 2:00 PM |
| Jun 13, 2026 | Saturday | `webinar_jun_13` | Fri 10:00 AM | Sat 2:00 PM |
| Jul 25, 2026 | Saturday | `webinar_jul_25` | Fri 10:00 AM | Sat 2:00 PM |
| Aug 15, 2026 | Saturday | `webinar_aug_15` | Fri 10:00 AM | Sat 2:00 PM |
| Sep 26, 2026 | Saturday | `webinar_sep_26` | Fri 10:00 AM | Sat 2:00 PM |

---

## Merge Tags Reference

| Tag | Source | Description |
|-----|--------|-------------|
| `{{contact.first_name}}` | GHL Contact | Attendee first name pulled from Eventbrite |
| `{{contact.zoom_access_details}}` | Custom Field | Set by Update Contact Field step per branch |

---

## Important Notes

**Late registrations**  
If someone registers on the same day as the webinar, Wait 1 (day before) will be skipped by GHL and the email may send immediately or not at all. This is expected behavior with Time Delay + Advance Window.

**Zoom links**  
Each branch must have its own correct Zoom link in the Update Contact Field step. Always verify the link is active before each webinar.

**CAN-SPAM compliance**  
All contacts in this workflow opted in via Eventbrite registration. Do not add cold leads (contacts from 2025 and earlier) to this workflow without running a re-engagement sequence first.

**One Zap per webinar date**  
The Zapier setup requires a separate Zap for each Eventbrite event. Each Zap adds a unique date tag that routes the contact to the correct GHL branch.

---

## Maintenance Checklist

Run this checklist each time a new webinar is created:

- [ ] Create new event on Eventbrite
- [ ] Duplicate the Zap in Zapier
- [ ] Update the Eventbrite event ID in the new Zap
- [ ] Update the date tag in the new Zap (e.g. `webinar_aug_15`)
- [ ] Activate the new Zap
- [ ] Add new branch in GHL workflow with correct tag condition
- [ ] Add Update Contact Field with the correct Zoom link
- [ ] Verify Wait 1 — Resume On: Friday, Exact: 10:00 AM
- [ ] Verify Wait 2 — Resume On: Saturday, Exact: 2:00 PM
- [ ] Send a test contact through the workflow
- [ ] Confirm both reminder emails arrive at the correct times

---

*Last updated: April 2026*  
*Maintained by: Marketing Team — Live Life With Zest*
