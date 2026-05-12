# Cold Leads Email Campaigns — May 2026

## Context

All contacts in these campaigns are cold leads imported from LinkedIn. The CRM is currently being organized and segmented. Since we do not yet have enough data to send topic-specific emails, we are sending broad campaigns to all contacts and tracking their behavior via click tags. This allows us to identify interests organically and build qualified segments for future targeted campaigns.

---

## Campaign 1 — Female Re-engagement (Mixed Topics)

**Smart List:** `cold-leads-no-location` (Batch 1) → `female-not-contacted` (Batch 2)
**Audience:** Female cold leads imported from LinkedIn
**Goal:** Re-introduce Madelaine, invite contacts to self-select their topic of interest

**Subject:**
```
Hi {{contact.first_name}}, we met on LinkedIn — this is for you 👋
```

**Body:**
```
Hi {{contact.first_name}},

My name is Madelaine Romero. We connected on LinkedIn a while back, 
and I've been thinking about reaching out ever since.

I work with women who are exhausted, overwhelmed, and ready to finally 
put themselves first — and I host free webinars to help them do exactly that.

I'd love to invite you to one of our upcoming sessions.
Pick the topic that speaks to you most right now:

👉 Thriving Through Menopause
https://www.eventbrite.com/e/3-truths-every-woman-needs-to-know-to-thrive-in-menopause-tickets-1587094374999?aff=oddtdtcreator

👉 From Burnout to Balance
https://www.eventbrite.com/e/from-burnout-to-balance-a-practical-plan-for-women-in-healthcare-tickets-1596258294529?aff=oddtdtcreator

👉 Weight Loss for Women in Healthcare
https://www.eventbrite.com/e/the-diet-myths-preventing-women-in-healthcare-from-losing-weight-tickets-1984950471293?aff=oddtdtcreator

And if you're looking for something more than a one-time session,
we built something just for that.

The Zest Collective is our private community for women who are done 
running on empty and ready to reclaim their energy, their health, 
and their lives. It's free to join.

👉 Join The Zest Collective:
https://www.livelifewithzest.com/the-zest-collective

Just click the topic that resonates — I'll save you a seat.

Warmly,
Madelaine Romero
Live Life with Zest
www.livelifewithzest.com
```

**Tags configured per link:**

| Link | Tag |
|------|-----|
| Thriving Through Menopause | `clicked-menopause` |
| From Burnout to Balance | `clicked-burnout` |
| Weight Loss for Women in Healthcare | `clicked-weightloss` |
| Join The Zest Collective | `clicked-zestcollective` |

**Batches:**

| Batch | List | Size | Date | Status |
|-------|------|------|------|--------|
| Batch 1 | `cold-leads-no-location` | 18 | May 1, 2026 | ✅ Sent |
| Batch 2 | `female-not-contacted` | 145 | May 6, 2026 | ⏳ Scheduled |

**Batch 1 Results:**

| Metric | Result |
|--------|--------|
| Delivered | 16 (88.89%) |
| Opened | 5 (31.25%) |
| Clicked | 0 (0%) |
| Unsubscribed | 0 |
| Bounced | 2 |

---

## Campaign 2 — Female Re-engagement (With Community)

**Smart List:** `female-not-contacted`
**Audience:** 145 female cold leads who had never opened an email
**Goal:** Same as Campaign 1 but with The Zest Collective community introduced as a second entry point for contacts not ready to register for a webinar

> Note: Mindful Money Circle was excluded from this email as it targets a US-specific insurance audience. This campaign focuses on health and wellness topics only.

---

## Campaign 3 — Male Insurance Outreach

**Smart List:** `male-contacts`
**Audience:** 143 male cold leads imported from LinkedIn
**Goal:** Introduce the concept of life insurance with living benefits and invite contacts to the Mindful Money Circle networking event

**Subject:**
```
{{contact.first_name}}, what protects your income if you can't work?
```

**Body:**
```
Hi {{contact.first_name}},

We connected on LinkedIn a while back, and I wanted to reach out personally.

I work with professionals on something most high-earners overlook, protecting 
their income, their family, and everything they've built if a serious illness 
ever pulls them out of the game, not if they die, but if they can't work.

I've seen it happen. A business owner diagnosed with cancer submitted a claim 
the same day, funds came through fast, and he focused entirely on recovery, 
not on keeping everything afloat. Another professional told me the biggest 
relief wasn't the treatment, it was knowing his mortgage was covered and his 
kids wouldn't have to leave college.

Most successful people have worked hard to build something real, but very few 
have a plan that protects it if they're suddenly unable to show up.

If this resonates, I'd love to invite you to a free online conversation with 
other professionals asking the same questions:

👉 Mindful Money Circle — Networking for Professionals
https://www.eventbrite.com/e/mindful-money-circle-networking-for-healthcare-professionals-tickets-1988841913702

No pitch. No pressure. Just a real conversation.

One note, this event is for US-based professionals only. If that's not you, 
feel free to unsubscribe. No hard feelings at all.

Warmly,
Madelaine Romero
www.livelifewithzest.com

*Not a solicitation of any specific insurance policy. 
Living benefits results vary by policy and qualifying event.*
```

**Tags configured:**

| Interaction | Tag |
|-------------|-----|
| Opened email | `insurance-opened` |
| Clicked any link | `insurance-clicked` |
| Clicked Mindful Money Circle | `clicked-mindful-money` |

---

## What Happens After Contacts Click

When a contact clicks a link and registers on Eventbrite, the existing Zapier integration automatically detects the registration, adds the correct webinar tags in GHL, and triggers the confirmation email and reminder workflow.

As contacts accumulate interest tags from these campaigns, Smart Lists will be refined to send topic-specific emails to the right person at the right time. This is how cold leads become qualified leads over time, through their own behavior.

---

## Next Steps

- [ ] Monitor Batch 2 results (female re-engagement)
- [ ] Send insurance campaign to male-contacts
- [ ] Build Smart Lists based on interest tags as clicks come in
- [ ] Community invitation campaign for 40 warm leads
- [ ] Scale female campaign to Batch 3 based on results

---

*Last updated: May 6, 2026*
*Maintained by: Marketing Team — Live Life With Zest*


