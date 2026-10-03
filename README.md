# Cornerstone Creative Capital — Company Brain

The governed operating memory of **Cornerstone Creative Capital LLC**, a
lender-facing LLC providing **EMD (earnest money deposit) loans** and **gap
funding**. Cornerstone also owns **DIBS** (Decentralized Infinite Bank-like
System), which is kept as a separate, gated domain.

This repo is where the rules, definitions, decisions, and agent skills that run
Cornerstone's deal flow are written and versioned. It is the authoring
environment; it is not the system of record for loan balances or wire receipts.

---

## Rule 1 — read before anything else

> **Loan funds are wired only to escrow. Never to the borrower or any other party.**
> *Owner: founder · Adopted 2026-10-03 · Status: current*

Escrow wire instructions are confirmed by a callback to an independently
sourced number (the title company's published line), never a number taken from
the email. Any instruction to pay anyone other than the escrow or title company
on the deal is a **stop**. No agent ever initiates, approves, or changes a wire.

---

## Current goal

| | |
| --- | --- |
| **Target** | 10 deals funded, Oct 3 → Dec 31, 2026 |
| **Measured by** | Deals entering the *Funded* stage (escrow confirms wire receipt) |
| **Ritual** | Monday deal review, 8:00 CT, off an agent briefing — starts Oct 12, 2026 |
| **Judge / date** | Founder · Monday, Jan 4, 2027 |
| **Access** | Founder-only until written access rules exist |

---

## Start here

| File | What it is |
| --- | --- |
| [`COMPANY-BRAIN-UPGRADE.md`](./COMPANY-BRAIN-UPGRADE.md) | The evaluation and sequenced build plan. Section 7 is the work; section 10 is open items. **Do not rename** — the build resumes from it by name. |

## Planned layout

Built in the order set out in `COMPANY-BRAIN-UPGRADE.md` §7. Nothing below
exists until its step is approved.

```
BRAIN.md                         # purpose, non-goals, source hierarchy, agent behavior
CLAUDE.md                        # navigation + durable rules only
company/
  products.md                    # current EMD and gap terms, dated
  glossary.md                    # EMD, gap, assignment, "funded", …
  decision-rights.md             # before anyone else joins
decisions/
  active/0001-funds-to-escrow-only.md
  superseded/                    # replaced rules, marked non-operative
domains/
  lending/stages.md              # pipeline stages, entry/exit/staleness
  dibs/README.md                 # gated — written before DIBS enters anything
governance/
  data-classification.md
  ingestion-rules.md
  agent-action-policy.md
sources/canonical-sources.yaml   # where each fact's truth lives
.claude/skills/
  monday-deal-review/
  new-request-triage/
  wire-instruction-check/
  deal-record-keeper/
```

## Deal stages (draft, pending founder approval)

Inquiry → Docs → Underwriting → Terms accepted → **Escrow verified** →
**Funded** → Paid off  · (Declined / Withdrawn from any stage)

## Working rules

- **Draft, never send.** Agents draft replies; the founder sends.
- **Current over old.** Replaced terms and rules move to `decisions/superseded/`
  and are never quoted as current.
- **Cite the source.** Every deal fact traces to an email thread or call.
- **Regulated data stays out.** Borrower SSNs, ID scans, bank statements, and
  credit reports are never copied into this repo or the brain.
- **Changes go through git.** One decision record per rule change, dated, with
  what it replaced.
