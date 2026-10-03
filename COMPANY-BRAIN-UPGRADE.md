# COMPANY-BRAIN-UPGRADE.md

**Cornerstone Creative Capital LLC: company brain upgrade plan**
Prepared October 3, 2026, in this repo (`dibs-financial/cornerstone-creative-capital-`).
Owner: the founder. Status: agreed definition of success (revision 2). Plan ready to execute.

> This file is read by name when work resumes. Do not rename it.

**Revision 2 (October 3, 2026).** The evaluation was re-run after the first
build steps landed and two new sources surfaced: the PML lender list
(185 private money lenders) and the LenderFlow Intake spec v1.2. Changes:
capital comes first in the definition of success (20 active lenders); the plan
adds a lender pipeline and a Capital Desk agent; LenderFlow becomes
Cornerstone's own intake portal (Cornerstone is the pilot customer, then the
product is sold to other lenders); automated lender outreach is in scope and
needs its own written rules. Superseded: revision 1's deal-flow-only definition
of success. It is no longer current.

---

## 1. Executive summary

**What you have.** A young brain built in the right order. The rules came
first: Rule 1 (funds only to escrow) is an active decision record, the deal
stages are approved, and three privacy and governance files are drafted
(PR #3). No data source is connected yet. Outside the repo you have two real
assets: a **185-lender PML network with about $107.6M in stated capacity**,
and a **build spec for LenderFlow Intake**, an intake portal. Deal flow still
runs on Gmail and your memory. There's no CRM and no meeting recorder.

**What success means to you** (agreed October 3, 2026, revision 2):

> By December 31, 2026: **20 active lenders** (first priority) and **10 deals
> funded**, each matched to the lender who funded it. Lender outreach is
> automated. LenderFlow is Cornerstone's intake portal, with Cornerstone as its
> pilot customer. The **Monday** review covers capital first, then deals.
> Access is founder-only, answers are cited, and **funds go only to escrow**.

**The upgrade, in one paragraph.** Finish the rules: approve the privacy files,
add a written exception that lets lender outreach send on its own (with
CAN-SPAM handling and a separate sending domain), and clean the lender list.
Then connect four sources:
- the meeting recorder;
- Gmail and calendar;
- LenderFlow, running for Cornerstone, as the front door for deals;
- the outreach tool's replies.

Then run two agents, both owned by you:
- **Capital Desk** takes each lender from contacted to active to funded a deal.
  Its outreach sends automatically within limits. Replies are triaged and
  answered as drafts.
- **Deal Desk** takes each request from intake to funded, and protects every
  wire.

One Monday briefing joins the two: lenders first, then deals, then which
lender fits each open deal. The first briefing goes out **Monday, October 12**.
Both numbers are judged on **Monday, January 4, 2027**.

**Both paths are real, and they differ in one place.** As one person with one
mailbox, you can run deals and lender replies on Claude Code with the Gmail
connector. Bulk outreach is different on any path: it belongs in a dedicated
sending tool on a separate domain, not in your main inbox. The brain's job is
to know every lender, read every reply, and match capital to deals. Section 6
compares the paths.

### What you keep, and what gets better

| What you have (stays) | What gets better with Day AI |
| --- | --- |
| This repo, its git history, Claude Code | It stays where you write the rules and skills. They deploy from here over MCP and run when you're offline, not only when your laptop is open. |
| The PML lender list (185 lenders, tiers WHALE → SMALL) | Each lender becomes a record in the graph with every email, call and deal tied to it. "Active" is computed from what actually happened, not from a spreadsheet column. |
| Your Gmail inbox | Lender replies, borrower threads and escrow threads land in one graph within minutes, governed by the inclusion and exclusion rules in `governance/ingestion-rules.md`. |
| LenderFlow Intake | It stays your portal and your product. A submission becomes a deal in the brain, tied to the borrower's email and calls, without being typed in twice. |
| **Rule 1: loan funds go only to escrow** | It becomes a workspace instruction every agent inherits. A wire request pointing anywhere else is flagged on arrival. |
| The approved deal stages (`domains/lending/stages.md`) | Every agent follows them. LenderFlow statuses map onto them, so the deals-funded count has a single source. |
| The Monday review you're starting | A briefing in your inbox at 7:30: new active lenders against the target of 20, deals funded against 10, and which lenders fit each open deal. |
| Google Calendar and your lender and borrower calls | Video calls are recorded and transcribed for free and attached to the lender or the deal. A lender's verbal "send me anything under $150k in Texas" is on record. |
| DIBS | It stays separate and gated until you write its rules. |

**Next step:** create the Day AI workspace at [day.ai/login](https://day.ai/login).
That requires one Professional Agent at $75/month, cancel anytime; teammates,
data and chat are free. Use coupon code **`UPGRADEMYBRAIN`** at checkout for a
free first month. Then come back to this repo in Claude Code and say so; the
build continues from section 7 of this document. Section 9 has the details.

---

## 2. Current state

### Inventory (re-surveyed October 3, 2026)

| What | Evidence | Status |
| --- | --- | --- |
| Repo | `dibs-financial/cornerstone-creative-capital-`. PRs #1 and #2 merged, #3 open. One contributor | Active |
| Constitution | `README.md` (purpose, Rule 1, goal) | Partial. `BRAIN.md`, `CLAUDE.md` and `company/` don't exist yet |
| Decisions | `decisions/active/0001-funds-to-escrow-only.md` | ✓ Current |
| Domains | `domains/lending/stages.md` | ✓ Approved |
| Governance | `governance/data-classification.md`, `ingestion-rules.md` (92 PML business domains), `agent-action-policy.md` | Drafted, in PR #3 |
| Skills | `.claude/skills/company-brain-evaluation/` (this evaluation) | No Cornerstone skills yet |
| Lender network | `PML-lenders-for-bots.csv`, provided by the founder, **kept out of the repo** (Confidential) | 185 lenders, $107.6M stated capacity |
| Intake portal | `LenderFlow_Intake_Spec_v1.2_Lovable.docx`, provided by the founder | A spec only. Not built yet |
| Email | Gmail / Google Workspace | In use, not connected |
| CRM / meeting recorder / Slack | none | Not in use |

### The lender list, as data (no personal details)

| Tier | Lenders | Notes |
| --- | --- | --- |
| WHALE | 10 | Stated capacity $1M–$30M |
| SHARK | 82 | Mostly $500k–$700k |
| GATOR | 56 | $100k–$450k |
| MINNOW | 18 | $50k–$80k |
| SMALL | 19 | $10k–$45k |

Other columns: `priority` (176 EMAIL, 9 CALL FIRST), `pnw` (12 marked YES; its
meaning isn't confirmed, see section 10) and `list_number` (2–8). 92 lenders
use a business domain; 92 use Gmail, Yahoo, iCloud, Proton or similar.

**Problems to fix before any automated send** (individual rows are named in
chat, not here, because lender names are Confidential):
- One row has "call or text" in the email field.
- One lender appears twice, with two emails and two capacities.
- One phone field reads "WhatsApp"; one phone number has an invalid area code.
- About 50 company rows have a company word in `first_name` (for example
  "Get" for two different firms), which a mail-merge would use as a greeting.

### Against the seven-layer reference shape

| Layer | Present? | Evidence or gap |
| --- | --- | --- |
| 1. Constitution | Partial | `README.md`. Missing `BRAIN.md`, `company/products.md` (terms), `company/glossary.md` |
| 2. Domains | Partial | `domains/lending/` ✓. Missing `domains/capital/` (lender stages, "active" definition) and `domains/lenderflow/` |
| 3. Decisions | ✓ | `0001`. Next: `0002` lender outreach exception |
| 4. Current state | No | `state/company-now.md` |
| 5. Procedures | No | The fleet in section 7, step 4 |
| 6. Source registry | Partial | Ingestion rules drafted. `sources/canonical-sources.yaml` not yet written |
| 7. Governance | Drafted | PR #3 |

### Ladder rung

**Below rung 1** (no connectors live), but with rung-3 rules already in place.
That's the right order, and it is rare.

### Honest strengths

- **Rules before data.** Rule 1, the stages and the privacy rules exist before
  a single email is ingested. Most builds do this the other way round and pay
  for it.
- **A real capital network.** 185 lenders, already tiered, with a contact
  preference marked. Most founders start capital-side work from nothing.
- **A spec that already agrees with the brain's rules.** LenderFlow never
  collects SSNs, keeps IDs and bank statements internal, has no auto-approval,
  and treats documents under the GLBA Safeguards Rule. The brain's
  classification says the same things independently.
- **Two numbers, one judge, one date.** 20 active lenders and 10 deals
  funded, judged by you on January 4, 2027.
- **You are the builder,** and you're already shipping the rules through pull
  requests.

---

## 3. Definition of success

Agreed in this session on October 3, 2026 (revision 2), in your words and
choices:

- **Capital first:** "Add the capital side" and "capital side first." Target:
  **"20 active lenders"** by December 31, 2026.
- **Deals:** **10 deals funded** by December 31, 2026, each matched to the
  lender who funded it.
- **LenderFlow:** "Both." Cornerstone is the pilot customer, then it's sold
  to other lenders.
- **Outreach:** "Yes, automated sends."
- **Ritual:** the Monday review, capital first, then deals.
- **Unchanged from revision 1:** founder-only access with written access rules
  before anyone joins; answers cited and current; **"Fund money only goes to
  escrow. Always."**

*Superseded:* revision 1's deal-flow-only definition (10 deals funded, no
capital target). Kept here for history; not current.

---

## 4. The bar

Every aspect below is graded against four requirements. A brain that misses
one of them is a prototype, not a finished brain.

1. **Safety.** Permissions are enforced in the store, per person. Ingestion is
   governed by explicit inclusion *and* exclusion rules. Credentials are per
   person, never one shared all-access login. Every value has a traceable
   source, and a source can be purged along with everything derived from it.
   For Cornerstone this covers borrower personal and financial data, wire
   instructions, and lenders' personal contact details.
2. **Performance.** Data lands continuously, within minutes. It's kept at full
   fidelity: whole threads and transcripts, not summaries. Retrieval is fast
   enough for an agent to brief you on a lender or a deal in seconds.
3. **Capability.** Things can fire when data arrives (a lender reply, a
   LenderFlow submission, a wire email, a recording), not only on a timer.
   Lender and deal records are created and updated from source material. Every
   source sits in one graph.
4. **Adoption.** It covers the whole team's data and use, once there is a
   team. People can talk back, and the agent changes. It adds **no data
   entry**.

---

## 5. Findings by aspect

### Capital: the PML lender network (new in revision 2)

**What you use:** a CSV of 185 private money lenders with name, email, phone,
stated capacity, tier, priority and list number. Outreach is planned to be
automated ("for bots").

**Captured in the company brain today:** the 92 business domains are in
`governance/ingestion-rules.md`, so their replies will be let in. Nothing else
yet. Which lenders are active, what each one funds (states, loan types, deal
sizes, terms), and who has replied all live in your head or nowhere.

**What's lost without it:**
- "Active" can't be counted, so the target of 20 can't be tracked.
- When a deal reaches underwriting, there's no quick answer to which lenders
  fund this size, in this state, this week.
- Replies get lost among borrower threads. One warm WHALE reply that goes
  unanswered for three days costs more than 50 cold emails.
- The data problems listed in section 2 would go straight into automated
  emails.

**Grade against the bar:**

| Requirement | Today | Gap |
| --- | --- | --- |
| Safety | A CSV with personal emails and phones, held outside the repo (good) | A Confidential lender record per person; an unsubscribe list that is honored everywhere; a sending domain separate from your main inbox |
| Performance | A static list | Each lender's status updated within minutes of a reply or call |
| Capability | No sends, no tracking | Outreach on a schedule; a reply moves the lender's stage and drafts the answer; a deal reaching Underwriting produces a lender shortlist |
| Adoption | You'd work the list by hand | You read the Monday count and answer warm replies, nothing else |

**Ideal outcome:** every lender has a record with tier, stated capacity,
lending criteria and stage. Outreach runs in capped daily batches from a
dedicated domain, with unsubscribes honored. Each reply moves the lender's
stage and gets a drafted answer within minutes. "Active" is computed from what
happened, and the count against 20 appears on Mondays. Each funded deal names
its lender.

**DIY path (honest):** a cold-email tool (any sequencing tool with warmup,
caps and unsubscribe handling) on a separate domain, plus a Google Sheet or
`lenders/*.md` for stages, plus a Claude Code skill that reads replies from
the tool or Gmail and updates the stages. Effort: about one week. Hazards: two
copies of lender status (the tool's and yours) that drift apart; unsubscribes
that have to be kept in sync by hand; personal contact data in a spreadsheet
anyone with the link can open.

**With Day AI:** lenders become people and organizations in the same graph as
deals. Replies arriving in Gmail are ingested and tied to the lender. Lender
stages can be a pipeline with AI-managed properties. *Verify in a demo
(section 10): whether Day AI sends bulk outbound sequences itself. Assume not.
The plan uses a dedicated sending tool on either path, with Day AI holding the
record and the replies.*

**Sequence:** step 2 (list cleanup, outreach rules) and step 3 (sending
domain, warmup). It goes first among the agents because the target is
capital first.

### Intake: LenderFlow (new in revision 2)

**What you use:** a build spec, v1.2, for Lovable (React/TypeScript on managed
Postgres): an eight-step submission form, a private document bucket, a staff
queue, and 10 internal statuses. It's a spec only, not built yet.

**Captured in the company brain today:** nothing.

**Fit with the brain:** strong. LenderFlow already enforces what
`data-classification.md` requires:
- no SSN, EIN or bank credentials are collected;
- IDs and bank statements are internal only and reached through short-lived
  links;
- the activity log can only be added to, never edited;
- nothing auto-approves.

That answers an open question from revision 1: **the LenderFlow private bucket
is the document vault** for Regulated borrower documents. The brain records
only "received" and the date.

**How LenderFlow statuses map onto our deal stages:**

| LenderFlow status | Brain stage (`domains/lending/stages.md`) |
| --- | --- |
| Draft | Not in the brain |
| Submitted | Inquiry |
| Missing Documents, Additional Information Requested | Docs |
| Under Review, Intake Complete | Underwriting |
| Terms Sent | Underwriting, with terms issued (exit pending the borrower's written acceptance) |
| On Hold | No stage change; flagged in the Monday briefing |
| Not Pursuing | Declined |
| Withdrawn | Withdrawn |
| *(no LenderFlow status)* | Terms accepted, Escrow verified, Funded, Paid off. These stay brain-only, which matches the spec's own rule "do not invent Funded" |

**Grade against the bar:**

| Requirement | Today | Gap |
| --- | --- | --- |
| Safety | Strong by design (row-level security, private bucket, append-only log) | Must pass the spec's own "Borrower A vs Borrower B" test before real files arrive |
| Performance | Not built | A submission reaches the brain within minutes |
| Capability | Not built | A submission creates the deal; a status change moves the stage; a deal reaching Underwriting triggers the lender match |
| Adoption | Not built | Borrowers submit once; you never re-type a deal |

**DIY path:** build LenderFlow per its spec (Prompts 0–8, about 1–2 weeks of
Lovable sessions). Add one Edge Function that posts each submission and status
change to a webhook. The brain side receives it: a `deals/` file in the DIY
version, a skill trigger in the always-on version. Hazard: LenderFlow and the
brain disagree when the webhook fails silently. The Monday briefing should
report its last-received event time.

**With Day AI:** the same Edge Function posts to Day AI through its API
(reference: the Day AI SDK, https://github.com/day-ai/day-ai-sdk). It creates
or updates the opportunity tied to the borrower's existing email and calls.
*Verify in a demo: inbound API or webhook for creating opportunities, and
idempotent updates.*

**Sequence:** step 3, after the privacy rules. It's built for Cornerstone
first; the commercial launch to other lenders comes after the pilot proves
out.

### Email

**What you use:** Gmail on Google Workspace, one mailbox. It carries borrower
requests, escrow and title correspondence, wire instructions, payoffs and,
from now on, **lender replies**.

**Captured today:** nothing is ingested yet. The draft inclusion and exclusion
rules exist (PR #3), including 92 PML business domains. The 92 lenders on
personal-provider addresses are matched from the lender list in the brain.

**Grade against the bar:**

| Requirement | Today | Gap |
| --- | --- | --- |
| Safety | Rules drafted, not enforced; no wire check | Rules enforced at ingestion; Rule 1 checked on every wire email; never exclude all of gmail.com |
| Performance | Nothing ingested | Within minutes, full threads |
| Capability | Nothing fires | A lender reply, a funding request or a wire email each trigger a skill |
| Adoption | You re-read threads | Status comes out of the email itself |

**DIY path:** reading on demand through the Gmail connector is feasible now.
Continuous ingestion means restricted Gmail API scopes plus Gmail's
undocumented rate limits, which can suspend API access to your own mailbox for
an unknown period. Governance and per-person permissions aren't a reasonable
solo build once a second person is involved. **And on any path:** don't send
bulk outreach from this mailbox. Spam complaints from cold email would damage
the deliverability of the inbox that carries your escrow threads.

**With Day AI:** Google Workspace connects under your own login, with
inclusion and exclusion by address, domain and label, per-thread permissions,
and email arrival as a skill trigger.

**Sequence:** step 3.

### Meeting recording

**What you use:** none. Lender calls (9 lenders are marked CALL FIRST),
borrower calls and escrow calls leave no record.

**Grade:** missing on all four requirements. Nothing is captured, nothing
fires, and there's no evidence of what was promised or quoted.

**Ideal outcome:** video calls with lenders and borrowers are recorded with
consent, transcribed, and attached to the lender or the deal. A lender's
stated criteria go straight onto their record. Phone calls are logged with a
short note to self, which enters the brain through the `Cornerstone` label
(rule I-1 in `ingestion-rules.md`).

**DIY path:** a commercial recorder plus a skill that pulls its transcripts.
That works, but the transcripts sit in a second silo. A custom recorder is
months of work.

**With Day AI:** per Day AI, a native, free, consent-handled recorder whose
transcripts land in the same graph. *Verify: phone calls are likely not
covered.*

**Sequence:** step 3, first item. It's free and the least sensitive source.

### CRM

**What you use:** none, and that is still an advantage. The lender pipeline and
the deal pipeline are both defined in this repo and filled from the sources.
Nothing is typed in by hand.

### Slack, product and engineering

Slack is out of scope. LenderFlow is the one software product. Its build
follows its own spec and its own issue tracking. If it moves to GitHub Issues
or Linear, run the product and engineering evaluation for it.

---

## 6. The three-way picture

| Aspect | Current state | DIY build-out (effort and hazards) | With Day AI (mechanism) |
| --- | --- | --- | --- |
| Rules and definitions | Rule 1, stages ✓; privacy drafted | Same on both paths: the files in this repo | The same files, also deployed as workspace instructions |
| Lender network | A CSV outside the repo | Sending tool + Sheet or `lenders/*.md` + reply skill. About a week. Status drifts between two copies | Lenders as records in the graph; replies tied to them; *outbound sending still via a dedicated tool (verify)* |
| Outreach sending | None | Dedicated domain + sending tool on both paths. Never your main inbox | Same |
| Intake (LenderFlow) | A spec | Build per the spec + webhook to `deals/`. 1–2 weeks | Build per the spec + webhook to the Day AI API |
| Email | Inbox only | On-demand connector: days. Continuous: weeks, plus a suspension risk | Native ingestion, governance, permissions |
| Meetings | Nothing | Commercial recorder in a second silo | Native free recorder in the same graph |
| Monday briefing | No meeting | A skill run by hand on Monday morning | Scheduled; delivered before you wake |
| Lender ↔ deal match | In your head | A skill run by hand on a deal | Fires when a deal reaches Underwriting |
| Wire check (Rule 1) | Your vigilance | Run by hand | Fires when a wire email lands |

**Bottom line:** capital-first raises the stakes on speed. Lender replies and
LenderFlow submissions arrive at any hour, and a reply answered three days
late doesn't make the target of 20. That's where events, as opposed to running
skills by hand, start to matter. Sending stays a separate tool on either path.

---

## 7. The upgrade plan, sequenced

Gates are marked **GATE**. Done items are marked ✓.

### Step 0: Outcome → workflow → where it breaks

| Outcome | Workflow | Where it breaks today |
| --- | --- | --- |
| **20 active lenders** | List → contact → reply → criteria on file → active → funds a deal | No sends; no record of replies or criteria; "active" undefined |
| **10 deals funded** | Intake (LenderFlow) → docs → underwrite → **match a lender** → terms → escrow verified → **wire to escrow** → payoff | No intake portal; status in your head; no lender match; wire check done by eye |

### Step 1: Constitution and rules

- ✓ `domains/lending/stages.md`: approved (PR #2).
- ✓ `decisions/active/0001-funds-to-escrow-only.md`: current (PR #2).
- `BRAIN.md`, `CLAUDE.md`, `company/glossary.md` (add PML, active lender,
  tier, CALL FIRST).
- `company/products.md`: current EMD and gap terms. **Needs your terms.**
- ✓ **`domains/capital/lender-stages.md`**: approved by the founder on 2026-10-03:

  | Stage | Enters when | Leaves when | Stale after |
  | --- | --- | --- | --- |
  | Listed | On the PML list, clean data | Contacted | — |
  | Contacted | First outreach sent (or a call, for CALL FIRST) | Replied, unsubscribed, or 3 touches without a reply | 21 days |
  | Replied | Any human reply | Qualified, or not interested | 3 days without your answer |
  | Qualified | Criteria on file: states, loan types, size range, terms, how they fund | Active | 14 days |
  | **Active** | **Qualified, and confirmed available capital within the last 60 days** (in writing or on a recorded call) | Funds a deal, or 60 days without confirmation | 60 days |
  | Funded a deal | Their money funded a Cornerstone deal (escrow-confirmed) | — | — |
  | Not interested / Unsubscribed | Any stage | — | Never contacted again |

  **Active lenders = lenders currently in Active or Funded a deal** (with a
  confirmation in the last 60 days). That's the Monday number against 20.
- **New: `domains/lenderflow/README.md`.** What LenderFlow is, the
  pilot-then-product plan, and the status mapping from section 5.

**GATE:** ✓ `lender-stages.md` approved 2026-10-03, including the definition of
"active".

### Step 2: Privacy and outreach rules (before any source connects or any email is sent)

- **PR #3** (`data-classification.md`, `ingestion-rules.md`,
  `agent-action-policy.md`), reviewed and merged. Still blank: escrow and
  title domains, personal contacts to exclude, retention after payoff
  (counsel). ✓ Answered: the vault is the LenderFlow private bucket.
- **`decisions/active/0002-lender-outreach-automated.md`** (drafted 2026-10-03, pending approval), a narrow
  exception to "never send unsupervised":
  - **Scope:** first-touch and follow-up emails to the PML list only. Never
    to borrowers, escrow, title or anyone else. Replies to lenders stay drafts
    you send.
  - **Content:** approved templates only. No terms, rates or deal specifics
    in automated emails. No attachments.
  - **CAN-SPAM:** a working unsubscribe link, a physical mailing address,
    honest subject lines, and opt-outs honored within 10 business days.
  - **Limits:** a separate sending domain (not your main mailbox); a warmup
    period; a daily cap (start at 30/day and raise only while bounces stay
    under 3% and complaints near zero); stop automatically if those
    thresholds are crossed.
  - **CALL FIRST lenders** (9) are never emailed first. A call task goes on
    the Monday list instead.
  - **Stop list:** Unsubscribed and Not interested lenders are never contacted
    again, in any tool.
- **Lender list cleanup** (the five problems in section 2). The list is kept
  in the brain as Confidential, never in this repo.

**GATE:** 0002 approved; the list is clean; the sending domain is
authenticated (SPF, DKIM, DMARC).

### Step 3: Connect sources, highest trust-to-value first

1. **Meeting recorder:** Meet and Zoom deal calls and lender calls.
2. **Gmail and Calendar:** under your own login, with the PR #3 rules
   applied. Backfill 90 days.
3. **Sending tool:** on the dedicated domain. Load the clean list, starting
   with the WHALE and SHARK tiers in sends 1–2 (92 lenders, the largest stated
   capacity). Replies route to Gmail so the brain sees them.
4. **LenderFlow for Cornerstone:** build per its spec (Prompts 0–8), pass the
   "Borrower A vs Borrower B" test, then add the webhook to the brain.
5. **`sources/canonical-sources.yaml`:**
   - lender stage comes from the lender record (derived from replies and
     calls);
   - deal intake comes from LenderFlow;
   - deal status after Terms accepted comes from email;
   - wire receipt comes from escrow's confirmation only;
   - unsubscribes come from the sending tool, mirrored into the brain.

**GATE (data readiness):** each of the 10 WHALE lenders has a correct record
(spot-check all 10); every deal you know is open exists; one test LenderFlow
submission arrives in the brain within 5 minutes.

### Step 4: The fleet, two agents and one shared briefing

**Agent 1: `Capital Desk`.** One job: build and keep 20 active lenders, and put
the right lender in front of each deal. Owner: you.

| Skill | Situation | Trigger | Bar | Empty case | Acts by |
| --- | --- | --- | --- | --- | --- |
| **`lender-outreach`** | Lenders on the list who haven't been contacted | Daily, weekdays 9:00 CT, under 0002's cap | Sends only to Listed/Contacted lenders who haven't unsubscribed, excluding CALL FIRST; ≤ the daily cap; stops on threshold breach | Nobody due: sends nothing, logs "0 due" | **Sends automatically** (the 0002 exception) |
| **`lender-reply-triage`** | A lender replies | Reply arrives in Gmail from a lender | Stage updated and answer drafted within 5 minutes; criteria extracted to the record with the source thread cited; unsubscribe or "not interested" goes straight to the stop list | Auto-reply or out-of-office: no stage change | Draft in Gmail, unsent; record updated |
| **`deal-lender-match`** | A deal needs capital | A deal enters Underwriting (from LenderFlow) | A shortlist of up to 5 Active lenders whose criteria fit the size, state and loan type, each with the reason and the source cited | No fit: "No active lender fits [criteria]. Closest: …" | Shortlist to you; introduction email drafted, unsent |

**Agent 2: `Deal Desk`.** One job: move every funding request toward funded
or a clean decline, and protect every wire. Owner: you.

| Skill | Situation | Trigger | Bar | Empty case | Acts by |
| --- | --- | --- | --- | --- | --- |
| **`new-request-triage`** | A request arrives by email instead of LenderFlow | Email with funding language from a new sender | Deal created; reply drafted with the LenderFlow submit link within 5 minutes | No funding language: does nothing | Draft, unsent |
| **`wire-instruction-check`** (Rule 1) | Any wire or bank instructions | Email with routing or account patterns, or a wire letter | Every one checked against the deal's verified escrow | Not wire-related: silent | **STOP** flag; never edits or forwards |
| **`deal-record-keeper`** (background) | Status moves | A LenderFlow event, email or recording | Stage updated with the source cited; old → new with date; LenderFlow mapping per section 5 | No change: silent | Writes; Funded / Paid off / Declined need your confirmation |

**Shared: `monday-review`** (cron, Monday 7:30 CT, about one phone screen):
1. **Capital:** active lenders against 20 and the weekly pace needed;
   lenders newly Replied, Qualified or Active; warm replies waiting on you;
   CALL FIRST calls due; outreach health (sent, bounce rate, unsubscribes).
2. **Deals:** deals funded against 10; every open deal with its stage, next
   step and matched lenders; payoffs due within 14 days; LenderFlow's
   last-received event time.
3. **Empty case:** "No change since last Monday. Pace needed: N lenders/week,
   M deals/week."

**DIY version:** the same skills in `.claude/skills/`, run by hand. Sending
goes through the sending tool's own scheduler. **Day AI version:** the same
prompts, deployed over MCP and triggered by events and the schedule.

### Step 5: Ignition plan

- **The standing meeting:** the Monday review, 8:00–8:30 CT, starting
  **Monday, October 12, 2026**.
- **The leader's numbers from the agent:** active lenders against 20, deals
  funded against 10. You quote them from the briefing, never from memory.
- **Owner of the managed skills:** you.
- **Crawl → walk → run:**
  - **Crawl (Oct 5 – Oct 25):**
    - rules and list cleanup (steps 1–2);
    - sending-domain warmup;
    - the LenderFlow build started;
    - the first WHALE outreach, done by hand: 10 lenders, the 9 CALL FIRST
      calls, and personal emails from you.
    - **Two-week test (Oct 26):** two Monday reviews run off the briefing;
      every WHALE lender has a stage.
  - **Walk (Oct 26 – Nov 22):**
    - automated outreach to SHARK, then GATOR, under the cap;
    - reply triage live;
    - LenderFlow live for Cornerstone;
    - `deal-lender-match` on.
    - **Checkpoint (Nov 23):** at least 10 active lenders.
  - **Run (Nov 23 – Dec 31):**
    - MINNOW and SMALL tiers added;
    - payoff watch and post-call lender-criteria capture on;
    - LenderFlow pilot reviewed for commercial launch.
- **Success bar:** **20 active lenders** and **10 deals funded** by
  **December 31, 2026**. Both come from records, each with a source. **Judge:**
  you. **Decision meeting:** Monday, January 4, 2027, with this section re-read
  word for word.
- **Hard floors, not targets:**
  - zero wires to a non-escrow payee;
  - zero emails to an unsubscribed lender;
  - outreach bounce rate under 3%.

### Step 6: Before anyone else joins

`company/decision-rights.md`; a separate login and connections per person; a
working month first. LenderFlow staff roles follow its own role table.

### Step 7: DIBS, gated

Unchanged. It's excluded until `domains/dibs/README.md` exists.

---

## 8. What stays yours

- **This repo is the authoring environment.** Rules, stages, decision records
  and skill prompts are written and versioned here.
- **LenderFlow is your product.** Its code syncs to GitHub per its spec. The
  brain reads its events; it doesn't own the portal.
- **The lender list and your lender relationships.** Kept in the brain as
  Confidential, never in git.
- **Your judgment.** Agents send only approved first-touch outreach under 0002.
  Everything else is a draft you send. No agent ever moves money.
- **Sunset on the Day AI path:** any interim `deals/` or `lenders/` files or
  Sheets from the DIY crawl.

---

## 9. Getting started with Day AI

**Where free ends and paid begins.** All pricing is public at
[day.ai/pricing](https://day.ai/pricing).

- **Free:** joining a workspace, adding data, querying it, chat in the web
  app, and the meeting recorder. Teammates come in free.
- **Paid:** creating a workspace requires a credit card and at least one
  **Professional Agent at $75/month**, month-to-month, cancel anytime. You need
  that agent yourself, because the MCP connection from this repo runs through
  your agent.
- **Later:** each agent deployed to a teammate is a subscription change with
  its own cost. Humans, data and chat are free; agents are what you pay for.
- **Not included either way:** the outreach sending tool and its domain, and
  LenderFlow's Lovable hosting (per its spec, from $25/month).
- **Coupon code `UPGRADEMYBRAIN`:** apply it at checkout at
  [day.ai/login](https://day.ai/login) for one month of the Professional Agent
  free, so month one is $0. It's a credit, not a trial; the card is charged
  from month two and you can cancel before then. One workspace per code.

**Steps:**

1. **Create the workspace** at [day.ai/login](https://day.ai/login) with code
   `UPGRADEMYBRAIN`.
2. **Come back to this repo in Claude Code and say so.** The Day AI MCP gets
   connected from this folder, this document is re-read, and section 7 is
   built step by step with your approval at each write. The privacy and
   outreach rules (step 2) go in before Gmail is connected or any email is
   sent.

Help: **support@day.ai** · Demo or consultation:
[day.ai/get-started](https://day.ai/get-started)

---

## 10. Open items

**To answer:**

1. **Approve `lender-stages.md`,** especially the definition of "active"
   (qualified plus capital confirmed within 60 days).
2. **`pnw` column:** what does "YES" mean on 12 lenders (proof of net worth?
   personal net worth?), and does it affect outreach order?
3. **How lender money moves:** does PML capital wire straight to escrow, or
   through Cornerstone first? Rule 1 covers disbursement to the deal either
   way. This changes how "Funded a deal" is confirmed.
4. **`list_number` column:** what do the values 2–8 mean (source list, batch)?
5. **Current terms** for EMD and gap loans (`company/products.md`).
6. **Baseline counts:** deals funded to date, and lenders already active
   today.
7. **Escrow and title domains; personal contacts to exclude** (PR #3).
8. **Counsel:**
   - record retention after payoff;
   - state licensing and usury for business-purpose EMD and gap loans;
   - CAN-SPAM and state rules for lender outreach;
   - whether lender outreach touches securities rules (raising capital from
     individuals). Confirm before the first automated send.
9. **LenderFlow commercial launch:** the spec targets Texas lenders. Is
   Cornerstone in Texas? When does the pilot become a product?
10. **DIBS:** what it is and whether it's in scope.

**To verify in a Day AI demo** (these come from Day AI's own materials and
were not independently tested):

- Whether Day AI sends bulk outbound sequences (the plan assumes not).
- An inbound API or webhook for creating and updating opportunities from
  LenderFlow; idempotency.
- Exclusion controls by label and attachment for Regulated documents.
- Recorder coverage for phone calls versus video calls; consent handling in
  your state.
- Skill triggers on an incoming email from a contact in a given pipeline (for
  `lender-reply-triage`).
- Exporting lender and deal records if you leave.
