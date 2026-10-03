---
id: lender-stages
status: current
owner: founder
approved_by: founder
date: 2026-10-03
source: founder approval, Claude Code session
supersedes: none
review_by: 2027-01-04
related: [domains/lending/stages.md, decisions/active/0002-lender-outreach-automated.md, governance/data-classification.md]
---

# Lender stages: private money lenders (PMLs)

One pipeline for every capital partner on the PML list. Each stage is written
so a new hire, or an agent, can place a lender correctly without asking.

| Stage | Enters when | Leaves when | Stale after |
| --- | --- | --- | --- |
| **Listed** | On the PML list with clean data (valid email or phone, real first name) | Contacted | — |
| **Contacted** | First outreach sent, or a call made for CALL FIRST lenders | Replied, Unsubscribed, or 3 touches without a reply | 21 days |
| **Replied** | Any human reply (auto-replies and out-of-office don't count) | Qualified, or Not interested | 3 days without the founder's answer |
| **Qualified** | Criteria on file: states, loan types (EMD, gap), size range, terms, how they fund | Active | 14 days |
| **Active** | Qualified, **and** confirmed available capital within the last 60 days, in writing or on a recorded call | Funds a deal, or 60 days without a fresh confirmation (back to Qualified) | 60 days |
| **Funded a deal** | Their capital funded a Cornerstone deal, confirmed by escrow | — (stays; needs a confirmation every 60 days to count as active) | 60 days |
| **Not interested** | Says no at any stage | — | Never contacted again |
| **Unsubscribed** | Opts out at any stage, in any tool | — | Never contacted again, in any tool |

## Definitions

- **Active lenders** = lenders in **Active** or **Funded a deal** whose capital
  was confirmed within the last 60 days. This is the Monday number, measured
  against the target of **20 by 2026-12-31**.
- **Confirmed available capital** = the lender said, in writing or on a
  recorded call, that they can fund now, with a size range. "Keep me posted"
  is not a confirmation.
- **Criteria** live on the lender's record in the brain (Confidential), never
  in this repo. Each one cites its source thread or call.

## Update modes

| Move | Mode |
| --- | --- |
| Listed → Contacted | Automatic when outreach sends (under `0002`) |
| Contacted → Replied, any → Unsubscribed / Not interested | Agent, from the reply or the sending tool; cites the source |
| Replied → Qualified | Agent proposes from the reply or call; founder confirms |
| Qualified → Active | Agent proposes on a capital confirmation; **founder confirms** |
| → Funded a deal | Agent proposes when the deal reaches Funded; founder confirms |
| Active → Qualified (lapsed) | Automatic after 60 days without a confirmation; reported on Monday |

## Order of outreach

WHALE, then SHARK, GATOR, MINNOW, SMALL. The 9 CALL FIRST lenders get a call
task in the Monday review and are never emailed first.
