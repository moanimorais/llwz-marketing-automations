# Cold Leads Re-engagement — Campaign Report

---

## CRM Overview

| Segment | Contacts |
|---------|----------|
| Total CRM contacts | 9,911 |
| Warm leads (2026) | 40 |
| Cold leads US (with location) | 22 |
| Cold leads no location | 9,846 |
| Contacts with valid email | 1,810 |

---

## Gender Segmentation

### Custom Field Created
A custom dropdown field **Gender** was created in GHL with options: Female, Male, Other.

### Process
1. Exported 1,810 contacts with valid emails from GHL
2. Used ChatGPT to classify names as Female, Male, or Unknown
3. Generated CSV with columns: Name, Email, Gender
4. Imported CSV via GHL Import tool (`/contacts/import`) using **Update contacts** mode
5. Mapped Email → Email, Gender → Gender (custom field)
6. Result: **1,810 contacts updated — 100% success, 0 errors**

### Gender Breakdown

| Gender | Contacts |
|--------|----------|
| Female | 157 |
| Male | 143 |
| Unknown | ~1,510 |

### Smart Lists Created

| List Name | Filter | Contacts |
|-----------|--------|----------|
| `warm-leads-2026` | Created = This year | 40 |
| `cold-leads-us` | Created before 2026 + Country = United States | 22 |
| `cold-leads-no-location` | Created before 2026 + Country is empty | 9,846 |
| `female-contacts` | Gender = Female | 157 |
| `male-contacts` | Gender = Male | 143 |
| `female-not-contacted` | Gender = Female + Last email opened date is empty | 145 |

> ⚠️ Male contacts will be targeted when a new insurance event is available.

---

## Re-engagement Email

Personal tone, references LinkedIn connection, invites contact to choose topic:

- 👉 Thriving Through Menopause
- 👉 From Burnout to Balance
- 👉 Weight Loss for Women in Healthcare
- 👉 The Zest Collective (community)

> Mindful Money Circle excluded — US-specific insurance audience. Separate campaign pending.

---

## Batch 1 Results

**Date:** May 1, 2026 | **Size:** 18 contacts | **Audience:** Mixed cold leads

| Metric | Result | Status |
|--------|--------|--------|
| Delivered | 16 (88.89%) | ✅ |
| Opened | 5 (31.25%) | ✅ Excellent |
| Clicked | 0 (0%) | ⚠️ |
| Unsubscribed | 0 | ✅ |
| Complained | 0 | ✅ |
| Bounced | 2 | ⚠️ Normal |

**Analysis:** 0% click rate due to audience mismatch — mixed industries. This is the content filter working correctly.

---

## Batch 2

**Date:** May 6, 2026 at 10:00 AM EST
**Audience:** `female-not-contacted` — 145 females, no prior email contact
**Track clicks:** ✅ | **Tags per link:** ✅

### Tags Configured Per Link

| Link | Tag |
|------|-----|
| Thriving Through Menopause | `clicked-menopause` |
| From Burnout to Balance | `clicked-burnout` |
| Weight Loss for Women in Healthcare | `clicked-weightloss` |
| Join The Zest Collective | `clicked-zestcollective` |

---

## Batch Schedule

| Batch | Size | Audience | Status |
|-------|------|----------|--------|
| Batch 1 | 18 | Mixed cold leads | ✅ Sent May 1, 2026 |
| Batch 2 | 145 | Female cold leads | ⏳ Scheduled May 6, 2026 |
| Batch 3 | TBD | Based on Batch 2 results | ⏳ Pending |
| Male contacts | 143 | Insurance campaign | ⏳ Pending new event |

---

## Important Notes

**Gender segmentation** — GHL has no native gender filter. Custom field created and populated via CSV import using ChatGPT name classification.

**US Only policy** — LinkedIn contacts have no confirmed location. Webinars are free and online so all females are included. Location confirmed when contacts register on Eventbrite.

**CAN-SPAM** — Contacts imported from LinkedIn without explicit opt-in. Sending in small batches with personal tone to minimize risk.

---

## Next Steps

- [ ] Monitor Batch 2 results
- [ ] Scale to Batch 3 based on results
- [ ] Insurance campaign for 143 male contacts — pending new event
- [ ] Community invitation campaign for 40 warm leads
- [ ] Update Unknown gender contacts as data becomes available

---

*Last updated: May 5, 2026*
*Maintained by: Marketing Team — Live Life With Zest*

---

## Lead Qualification — Cold to Warm

After the campaigns were sent, contacts who opened the email and did not unsubscribe were manually qualified as warm leads. This is the first step of the cold-to-warm funnel working in practice.

### Process
1. Filtered contacts in GHL by **Last email opened date = this week** + **Gender = Female**
2. Excluded unsubscribed contacts
3. Added tag `new_warm_leads` to all qualifying contacts
4. Added qualifying contacts to the **warm-leads-2026** Smart List for future campaigns

### Result
Contacts who engaged with the campaign without opting out are now segmented as warm leads and will receive the community invitation campaign as the next step in the funnel.

### Why this matters
Cold leads who open an email have shown the first signal of interest. By tagging and moving them to the warm list immediately, future campaigns can speak to them differently — with a higher level of trust and a more direct invitation.

```
Cold lead receives email
        ↓
Opens email + does not unsubscribe
        ↓
Tag added: new_warm_leads
        ↓
Added to: warm-leads-2026 Smart List
        ↓
Next: Community invitation campaign (The Zest Collective)
```

*Last updated: May 13, 2026*
*Maintained by: Marketing Team — Live Life With Zest*



