---
id: data-classification
status: draft
owner: founder
date: 2026-10-03
review_by: 2027-01-04
applies_to: every source, every agent, every person with access
related: [governance/ingestion-rules.md, governance/agent-action-policy.md, decisions/active/0001-funds-to-escrow-only.md]
---

# Data classification

Every piece of information Cornerstone handles is in one of five classes. The
class decides whether it enters the brain, who can see it, and what an agent may
do with it. **When in doubt, use the higher class.**

| Class | Cornerstone examples | Enters the brain? | Who sees it | Agent behavior |
| --- | --- | --- | --- | --- |
| **Public** | Published terms page, marketing copy, public property records | Yes | Anyone with access | Read, summarize, draft |
| **Internal** | Current terms (`company/products.md`), PML firm names and business domains, pipeline counts, stage definitions, this repo | Yes | Founder (later: team per `company/decision-rights.md`) | Read, summarize, draft; cite the source |
| **Confidential** | PML contact list (personal names, personal emails, phones, capacity, tier), borrower names and contact details, deal amounts, purchase contracts, assignment contracts, title commitments, payoff letters, escrow officer correspondence | Yes, scoped to its deal | Founder; later only people assigned to that deal | Read only within the deal it belongs to; never mention one borrower's details in another party's draft |
| **Restricted** | Wire instructions, escrow and bank account numbers, routing numbers, DIBS material | Wire emails: **yes, to run Rule 1 only**. DIBS: **no**, until `domains/dibs/README.md` exists | Founder only | Read only to run `wire-instruction-check`; show **last 4 digits only**; never forward, quote in full, or copy into a deal record |
| **Regulated** | SSNs, driver's license and passport scans, bank statements, credit reports, tax returns, any borrower identity document | **No. Excluded.** | Stays in Gmail or the document vault, founder only | Never read, summarized, or copied. The deal record notes "received, date" and nothing else |

## Rules that apply to every class

1. **Provenance.** Every fact in a deal record cites its source: thread
   subject + date, or call date. No source, no fact.
2. **Minimum exposure.** Briefings carry what's needed to decide, not
   everything known. Amounts and stages yes; contract text no.
3. **No reclassification by agents.** Only the founder can move information to
   a lower class, by editing this file.
4. **Purge on request.** If a borrower or partner asks for removal, the source
   thread and everything derived from it (deal notes, summaries) are deleted
   together. Log the purge date in the deal record, without the content.
5. **Repo is Internal at most.** Nothing Confidential, Restricted, or Regulated
   is ever committed to this git repo. Deal records live in the brain, not
   here.

## Open (founder to confirm)

- Is there a document vault outside Gmail (Google Drive folder, other) for
  Regulated borrower documents? Name it here.
- Retention: how long are Confidential deal records kept after payoff? Needs
  counsel's answer (plan §10, item 7).
