---
id: lending-stages
status: current
owner: founder
approved_by: founder
date: 2026-10-03
source: founder approval, Claude Code session
supersedes: none
review_by: 2027-01-04
---

# Deal stages — EMD loans and gap funding

One pipeline for both products. Each stage is written so a new hire, or an
agent, can place a deal correctly without asking.

| Stage | Enters when | Leaves when | Stale after |
| --- | --- | --- | --- |
| **Inquiry** | A funding request arrives | Docs requested, or declined | 1 business day with no founder reply |
| **Docs** | Founder has requested purchase contract, ID, exit plan | Docs complete | 3 days with no borrower reply |
| **Underwriting** | Docs complete | Terms issued, or declined | 2 days |
| **Terms accepted** | Borrower accepts terms in writing | Escrow verified | 2 days |
| **Escrow verified** | Escrow company and wire instructions confirmed by independent callback (Rule 1, `decisions/active/0001-funds-to-escrow-only.md`) | Wire sent | 1 day |
| **Funded** | Escrow confirms receipt of the wire | Payoff received, or default | — |
| **Paid off** | Payoff received | — | — |
| **Declined / Withdrawn** | Any stage | — | — |

## Definitions

- **Deals funded** = deals that entered **Funded** in the period. This is the
  Monday number, measured against the target of 10 by 2026-12-31.
- **Funded** requires escrow's confirmation of receipt. A wire sent is not a
  deal funded.

## Update modes

| Move | Mode |
| --- | --- |
| Inquiry → Docs → Underwriting → Terms accepted | Agent may update from email/call evidence, citing the source thread |
| → Escrow verified | Founder only (callback is a human step) |
| → Funded | Agent proposes on escrow receipt email; founder confirms |
| → Paid off, Declined / Withdrawn | Agent proposes; founder confirms |

Stale deals are listed in the Monday deal review with days since last activity.
