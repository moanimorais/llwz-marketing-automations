# Cold Leads Re-engagement Strategy

Documentation for the re-engagement campaign targeting cold leads (imported from LinkedIn, pre-2026).

---

## Overview

**Total CRM contacts:** 9,911  
**Cold leads (pre-2026, no location):** 9,846  
**Warm leads (2026):** 40  
**Cold leads US (with location):** 22  

Most cold leads were imported from LinkedIn in October 2025 and have never received an email from Live Life With Zest. They have no defined interest tags, no gender data, and most have no country field populated.

**Goal:** Re-engage cold leads, identify their interests, and route them into the correct webinar funnel automatically via Eventbrite + Zapier.

---

## Smart Lists Created

| List Name | Filter | Contacts |
|-----------|--------|----------|
| `warm-leads-2026` | Created = This year | 40 |
| `cold-leads-us` | Created before 2026-01-01 + Country = United States | 22 |
| `cold-leads-no-location` | Created before 2026-01-01 + Country is empty | 9,846 |

> ⚠️ GHL Advanced Filters does not support filtering by Tags. Smart Lists are built using Created date and Country fields only.

---

## Why We Can't Filter by Gender

GHL does not have a native Gender field in Advanced Filters. Options considered:

- **Custom field** — rejected. Would require manually filling 9,911 records.
- **Name analysis** — rejected. Unreliable for international and gender-neutral names.
- **Interest-based segmentation** — selected. Let contacts self-identify by clicking the topic that resonates with them.

Since all current active webinars are targeted at women in healthcare, the email tone and content naturally filters the audience. Men who are not the target audience will simply not engage.

---

## Re-engagement Email

### Audience
`cold-leads-no-location` — 9,846 contacts imported from LinkedIn (October 2025)

### Soft Launch Approach
Send to **20 contacts first**, monitor metrics for 48 hours, then scale.

| Batch | Size | Condition to proceed |
|-------|------|---------------------|
| Batch 1 | 20 | Always |
| Batch 2 | 100 | Open rate > 20%, Unsubscribe < 2% |
| Batch 3 | 500+ | Consistent results from Batch 2 |

---

### Subject Line
```
Hi {{contact.first_name}}, we met on LinkedIn — this is for you 👋
```

### Body
```
Hi {{contact.first_name}},

My name is Madelaine Romero. We connected on LinkedIn a while back, 
and I've been thinking about reaching out ever since.

I work with women in healthcare who are exhausted, overwhelmed, and 
ready to finally put themselves first — and I host free webinars to 
help them do exactly that.

I'd love to invite you to one of our upcoming sessions.
Pick the topic that speaks to you most right now:

👉 Thriving Through Menopause
https://www.eventbrite.com/e/3-truths-every-woman-needs-to-know-to-thrive-in-menopause-tickets-1587094374999?aff=oddtdtcreator

👉 From Burnout to Balance
https://www.eventbrite.com/e/from-burnout-to-balance-a-practical-plan-for-women-in-healthcare-tickets-1596258294529?aff=oddtdtcreator

👉 Weight Loss for Women in Healthcare
https://www.eventbrite.com/e/the-diet-myths-preventing-women-in-healthcare-from-losing-weight-tickets-1984950471293?aff=oddtdtcreator

👉 Mindful Money Circle
https://www.eventbrite.com/e/mindful-money-circle-networking-for-healthcare-professionals-tickets-1986328509041?aff=oddtdtcreator

All sessions are free, online, and designed for busy women 
who don't have time to waste.

Just click the topic that resonates — I'll save you a seat.

Warmly,
Madelaine Romero
Live Life with Zest
www.livelifewithzest.com
```

---

## How the Funnel Works After the Email

When a contact clicks a link and registers on Eventbrite:

```
Contact clicks Eventbrite link
        ↓
Contact registers on Eventbrite
        ↓
Zapier detects new attendee
        ↓
Zapier adds tags to contact in GHL:
  - "thriving through menopause" + "webinar_may_23" (or date tag)
  - OR "burnout" tag
  - OR "weight loss" tag
  - OR "mindful money" tag
        ↓
GHL Workflow triggers
        ↓
Contact receives confirmation email + reminder sequence
```

No manual tagging required. Interest is captured automatically at the moment of registration.

---

## Metrics to Monitor

Check results 48 hours after each batch send:

| Metric | Good | Warning | Stop |
|--------|------|---------|------|
| Open rate | > 20% | 10–20% | < 10% |
| Click rate | > 5% | 2–5% | < 2% |
| Unsubscribe rate | < 1% | 1–2% | > 2% |
| Spam report | 0% | — | Any report |

---

## Active Webinar Links

| Webinar | Audience | Eventbrite Link |
|---------|----------|----------------|
| Thriving Through Menopause | Women in healthcare | [Link](https://www.eventbrite.com/e/3-truths-every-woman-needs-to-know-to-thrive-in-menopause-tickets-1587094374999?aff=oddtdtcreator) |
| From Burnout to Balance | Women in healthcare | [Link](https://www.eventbrite.com/e/from-burnout-to-balance-a-practical-plan-for-women-in-healthcare-tickets-1596258294529?aff=oddtdtcreator) |
| Weight Loss for Women in Healthcare | Women in healthcare | [Link](https://www.eventbrite.com/e/the-diet-myths-preventing-women-in-healthcare-from-losing-weight-tickets-1984950471293?aff=oddtdtcreator) |
| Mindful Money Circle | Women in healthcare | [Link](https://www.eventbrite.com/e/mindful-money-circle-networking-for-healthcare-professionals-tickets-1986328509041?aff=oddtdtcreator) |

> ⚠️ Insurance webinars are currently not active. Male contacts in the list will not be targeted until a new insurance event is created.

---

## Important Notes

**CAN-SPAM Compliance**
These contacts were imported from LinkedIn and did not explicitly opt in to email marketing. To minimize risk:
- Send in small batches (20 → 100 → 500+)
- Monitor unsubscribe and spam rates closely
- Use a personal, non-promotional tone
- Always include an unsubscribe link

**Gender segmentation**
Not possible at this stage due to lack of data. Current strategy relies on content relevance to naturally filter the audience. All active webinars target women in healthcare.

**Male contacts**
Approximately unknown number of male contacts exist in the list. They will be targeted when a new insurance or neutral topic webinar is created. No action for now.

---

## Next Steps After Results

- [ ] Monitor Batch 1 (20 contacts) for 48 hours
- [ ] If metrics are good → send Batch 2 (100 contacts)
- [ ] Track which webinars get the most registrations
- [ ] Update Smart Lists as new tags are added via Zapier
- [ ] Create insurance campaign when new event is available
- [ ] Document results in this file

---

*Last updated: April 2026*
*Maintained by: Marketing Team — Live Life With Zest*


