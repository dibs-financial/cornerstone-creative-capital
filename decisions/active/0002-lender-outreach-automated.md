---
id: 0002
title: Automated outreach to the PML list
status: draft
date: 2026-10-03
owner: founder
decision_makers: [founder]
scope: First-touch and follow-up emails to lenders on the PML list only
supersedes: none
exception_to: governance/agent-action-policy.md, never-list item 3 ("Send email unsupervised")
review_by: 2026-11-23
source: Founder, Claude Code session, 2026-10-03 — "Yes, automated sends"
---

# 0002: Automated outreach to the PML list

## Decision

The `lender-outreach` skill may send emails **without the founder pressing
send**, only inside the limits below. This is the only exception to "agents
never send unsupervised." Everything outside these limits is still a draft.

## Context

The first priority is **20 active lenders by 2026-12-31**
(`domains/capital/lender-stages.md`). The PML list has 185 lenders. Writing
each first email by hand doesn't fit the founder's time. Automated sending
brings legal, deliverability and reputation risk, so it gets narrow, written
limits.

## Scope: what may be sent automatically

- **To:** lenders on the PML list in **Listed** or **Contacted**. Never to
  Unsubscribed, Not interested, or CALL FIRST lenders.
- **What:** first touch plus at most **2 follow-ups**, at least 5 business days
  apart. Then the lender stays Contacted until the 21-day stale rule applies.
- **Content:** **approved templates only**, each committed under
  `templates/outreach/` and approved by pull request. No rates, terms, deal
  specifics, return figures or attachments. No promise of returns.
- **Never automatic:** any reply to a lender who has replied (drafts only); any
  email to a borrower, escrow, title company or anyone else.

## Guardrails

1. **Separate sending domain.** Outreach goes from a dedicated domain and
   mailbox, **never** the founder's main inbox. Replies route to Gmail so the
   brain sees them.
2. **Authentication and warmup.** SPF, DKIM and DMARC pass before the first
   send. Warm up for at least 14 days.
3. **Daily cap.** Start at **30 per day**. Raise by 10 per week at most, and
   only while bounces stay **under 3%** and spam complaints **under 0.1%**.
4. **Automatic stop.** Sending pauses on its own if bounces reach 3% or
   complaints reach 0.1% in any day. Resuming needs the founder.
5. **CAN-SPAM.** Every email has a working one-click unsubscribe, the
   company's physical mailing address, a truthful From line, and a subject that
   matches the content. Opt-outs are honored immediately; the law's outer limit
   is 10 business days.
6. **One stop list.** An unsubscribe or "not interested" anywhere (the sending
   tool, a reply, a call) puts the lender on the stop list in every tool, for
   good.
7. **Clean data first.** No lender is emailed until their row passes the
   Listed entry check: valid email, a real first name, no duplicate.
8. **Order.** WHALE, then SHARK, GATOR, MINNOW, SMALL.
9. **Counsel first.** No automated send until counsel confirms that outreach
   to individual lenders about capital doesn't need securities filings or
   disclosures. Record the answer here.

## Consequences

- Outreach goes on without the founder, so the founder's time goes to warm
  replies and CALL FIRST calls.
- One more tool to pay for and keep healthy (the sending tool and its domain).
- The Monday review reports outreach health: sent, bounce rate, complaints,
  unsubscribes.

## Evidence

- Founder answer, 2026-10-03: "Yes, automated sends." Recorded in
  `COMPANY-BRAIN-UPGRADE.md` §3 and §7, step 2.

## Before this becomes current

- [ ] Founder approves this record (merge of its pull request).
- [ ] Counsel's answer recorded (guardrail 9).
- [ ] Sending tool and domain chosen and recorded here: ________
- [ ] Physical mailing address for the footer: ________
- [ ] First templates approved under `templates/outreach/`.

## What would change our mind

Founder to fill in. Suggested: a complaint rate above 0.1% for two weeks
running, or counsel advising against it.
