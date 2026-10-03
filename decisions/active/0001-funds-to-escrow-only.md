---
id: 0001
title: Loan funds go only to escrow
status: current
date: 2026-10-03
owner: founder
decision_makers: [founder]
scope: All Cornerstone Creative Capital loans — EMD and gap funding, every deal, every disbursement
supersedes: none
review_by: 2027-01-04
source: Founder, Claude Code session, 2026-10-03 — "Fund Money only goes to escrow Always"
---

# 0001 — Loan funds go only to escrow

## Decision

Cornerstone disburses loan funds **only** to the escrow or title company on the
deal. Never to the borrower, a wholesaler, a seller, an assignee, or any other
party. No exceptions.

## Context

Cornerstone makes short-duration EMD loans and gap funding, mostly to
real-estate investors. Escrow is the neutral party that holds the money against
the transaction. Paying anyone else breaks the protection the loan depends on
and removes the clean payoff path.

Wire instructions arrive by email, and email is where wire fraud happens:
spoofed or compromised accounts send "updated" instructions that redirect funds.
A rule that the payee is always the deal's escrow company is simple enough to
check every time.

## Alternatives considered

- **Direct-to-borrower disbursement:** rejected. No neutral party, no
  protection, no clean payoff.
- **Case-by-case exceptions with founder sign-off:** rejected. Exceptions are
  the pattern fraudsters exploit; "Always" means always.

## Consequences

- A deal cannot reach **Funded** (`domains/lending/stages.md`) without passing
  **Escrow verified**.
- Borrowers asking for funds to themselves or a third party are declined or
  redirected to escrow.
- Some deals may move slower when escrow is slow to confirm. Accepted.

## Guardrails

1. **Payee check:** the receiving account belongs to the escrow or title
   company named on the deal. Anything else is a **STOP**.
2. **Independent callback:** escrow wire instructions are confirmed by phone
   using a number found independently (the title company's published number),
   **never** a number taken from the email carrying the instructions.
3. **Changed instructions are a STOP:** any email that changes previously
   verified wire instructions halts the deal until a fresh callback is done.
4. **Agents never move money:** no agent initiates, approves, or changes a
   wire. The `wire-instruction-check` skill flags; the founder decides.
5. **Funded means received:** a deal is Funded only when escrow confirms
   receipt, not when the wire is sent.
6. **Restricted data:** account numbers appear in briefings as last 4 digits
   only.

## Evidence

- Founder statement, 2026-10-03, in the session that produced
  `COMPANY-BRAIN-UPGRADE.md` (§3, §7 step 1).

## What would change our mind

*Founder to fill in, or leave as "nothing."*
