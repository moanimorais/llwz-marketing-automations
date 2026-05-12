# Incident Report — Email Sending Block

**Date:** May 6, 2026  
**Detected by:** Marketing Team (self-identified, no external alert)  
**Severity:** High — all email sending suspended mid-campaign  
**Status:** Resolved

---

## What Happened

During the May 6, 2026 email campaign send — which included the female re-engagement Batch 2 (145 contacts) and the male insurance outreach (143 contacts) — 142 emails were marked as **Failed** mid-send. All remaining email sending was suspended automatically by the GoHighLevel system.

The block was not flagged by any external alert. It was identified by the marketing team while reviewing the Bulk Actions dashboard during the active campaign send.

---

## Timeline

| Time | Event |
|------|-------|
| 10:00 AM EST | Both campaigns begin sending to 288 contacts |
| ~10:15 AM EST | Bounce rate crosses the 5% automatic threshold |
| ~10:15 AM EST | GHL auto-block activates — remaining 142 emails marked as Failed |
| 10:30 AM EST | Marketing team identifies the Failed count in Bulk Actions dashboard |
| 11:00 AM EST | Root cause investigation completed |
| 11:30 AM EST | Incident documented and corrective action plan sent to account owner |
| May 7, 02:01 AM UTC | Email sending services automatically restored after 12-hour suspension |

---

## Impact

| Metric | Result |
|--------|--------|
| Emails attempted | 179 |
| Emails delivered | 155 (87%) |
| Emails failed (never sent) | 142 (44%) |
| Bounced | 24 (13%) |
| Campaigns affected | Female Re-engagement Batch 2, Male Insurance Outreach |
| Duration of block | ~12 hours |

> The 142 failed contacts were NOT lost. They were never reached and can be included in the next batch once the account is correctly configured.

---

## Root Cause Analysis

Two configuration issues contributed to the high bounce rate that triggered the block:

**Issue 1 — Sending email address**
The account was configured to send from `rmadelaine@yahoo.com`. Yahoo addresses are frequently blocked or filtered by receiving email servers when used for bulk sending, causing a higher rate of hard bounces than expected.

**Issue 2 — Email Verification not enabled**
The GHL setting "Verify Email Address when first email is sent to a new contact" was not active. This means invalid or non-existent email addresses in the LinkedIn-imported contact list were not filtered before sending, allowing undeliverable addresses to enter the send queue and generate bounces.

Both issues combined pushed the bounce rate above GHL's automatic 5% threshold, triggering the system block.

---

## What Was Not the Problem

- Email content — zero spam complaints across both campaigns
- Subject lines — 29% open rate confirms strong deliverability for emails that did arrive
- Audience targeting — 6% click rate confirms the content resonated with those who received it
- Campaign configuration — Smart Lists, tags, and workflows were all set up correctly

---

## Corrective Actions

### Immediate (Marketing Team)
- [x] Identified root cause without external prompt
- [x] Documented incident and notified account owner with full report
- [x] Prepared re-send plan for the 142 failed contacts
- [x] Flagged 24 bounced contacts for suppression from future sends

### Required from Account Owner (Madelaine)
- [ ] Enable "Verify Email Address when first email is sent to a new contact" — Settings → Email Services
- [ ] Change sending email from `rmadelaine@yahoo.com` to `madelaine@livelifewithzest.com` — Settings → Email Services → From Email
- [ ] Add `livelifewithzest.com` as the Branded Domain — Settings → Business Profile → Branded Domain

---

## Lessons Learned

**1. Validate email addresses before any bulk send**
For imported lists (especially LinkedIn exports), email verification should always be enabled before launching a campaign. Cold lists have a significantly higher rate of invalid addresses than opted-in lists.

**2. Never use a personal or free email provider as the sending address**
Yahoo, Gmail, and Hotmail addresses are not built for bulk sending. A branded domain email (`@livelifewithzest.com`) improves deliverability, reduces bounce rates, and builds domain reputation over time.

**3. Send in smaller batches for new or unverified lists**
Starting with 18 contacts in Batch 1 was the right approach. Batch 2 (145 contacts) was still a manageable size, but for future sends to unverified LinkedIn-imported lists, keeping batches under 50 until domain reputation is established is recommended.

**4. Monitor Bulk Actions dashboard during active sends**
The issue was caught mid-send by actively monitoring the dashboard. Automated alerts (if available in the plan) should be configured for bounce rate thresholds.

---

## Prevention Checklist for Future Campaigns

Before any campaign send, verify the following:

- [ ] Email Verification is enabled in GHL settings
- [ ] Sending email is a branded domain address (not Yahoo/Gmail)
- [ ] Branded Domain is configured in Business Profile
- [ ] Contact list has been filtered for known bounces and unsubscribes
- [ ] Batch size is appropriate for the list quality (smaller for cold/unverified lists)
- [ ] Track clicks is enabled
- [ ] Tags per interaction are configured
- [ ] A test email has been sent and reviewed before launch

---

*Last updated: May 7, 2026*  
*Documented by: Marketing Team — Live Life With Zest*


