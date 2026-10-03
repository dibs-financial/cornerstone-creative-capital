# COMPANY-BRAIN-UPGRADE.md

**Cornerstone Creative Capital LLC: company brain upgrade plan**
Prepared October 3, 2026, in this repo (`dibs-financial/cornerstone-creative-capital-`).
Owner: the founder. Status: agreed definition of success. Plan ready to execute.

> This file is read by name when work resumes. Do not rename it.

---

## 1. Executive summary

**What you have.** A new repo with one file, `README.md`. Deal flow runs on
Gmail, Google Workspace and your own memory. There's no CRM, no meeting
recorder, no written rules and no weekly review. That is a normal place for a
founder-led lender to start, and it makes building easier: there's no legacy
system to migrate and no bad data to clean up. The brain can be built right the
first time.

**What success means to you** (agreed October 3, 2026):

> Within 90 days, Cornerstone runs its deal flow off the brain. Target:
> **10 deals funded.** Every EMD and gap-funding request in Gmail is tracked to
> funded, declined or paid off. Access is founder-only, with written rules
> before anyone else joins. A **Monday** deal review runs off an agent briefing.
> Answers come back current and cited. **Loan funds go only to escrow.**

**The upgrade, in one paragraph.** First, write down the rules: the escrow-only
rule, the deal stages, and what never enters the brain (borrower Social
Security numbers, bank statements, DIBS material until you decide otherwise).
Then connect your Gmail and calendar so every borrower, escrow officer and
title company thread lands in one place tied to the right deal. Then turn on
three agents' worth of work, owned by you:
- **Monday deal review:** a briefing in your inbox before 8:00 on the deals
  funded count against the target of 10, deals waiting on documents, deals
  waiting on escrow, and payoffs coming due.
- **New-request triage:** when a funding request lands, a drafted reply and a
  deal record.
- **Wire-instruction check:** any email carrying wire instructions is checked
  against the escrow-only rule before a dollar moves.

The first briefing goes out **Monday, October 12**. The count is judged on
**Monday, January 4, 2027**.

**Both paths are real.** You're one person with one mailbox, so the hardest
part of a do-it-yourself build doesn't apply to you yet: that's email shared
across a team, with per-person permissions. A careful solo build on Claude Code
and the Gmail connector can carry you through the 90 days. The limits arrive
when you add the first teammate or investor-relations helper, when you want
skills to fire the moment an email lands instead of when you open your laptop,
and when you want calls captured as transcripts. Section 6 shows where each
path stands.

### What you keep, and what gets better

| What you have (stays) | What gets better with Day AI |
| --- | --- |
| This repo, its git history, Claude Code | It stays where you write the rules and skills. They deploy from here over MCP and run when you're offline, not only when your laptop is open. |
| Your Gmail inbox | Every borrower, escrow and title thread is in one graph, tied to the right deal, updated within minutes. Inclusion and exclusion rules mean personal mail and anything you flag stay out. |
| Google Calendar and your borrower / escrow calls | Zoom, Meet and Teams calls are recorded and transcribed for free and attached to the deal. What a borrower promised on the call is on the record. |
| **Rule 1: loan funds go only to escrow** | It becomes a workspace instruction every agent inherits. A wire request pointing anywhere else is flagged on arrival, not when you happen to reread the thread. |
| Deals funded, counted in your head today | The Monday briefing reports the count against the target of 10, from the deal records the agents keep current from email. You don't have to type it anywhere. |
| The Monday deal review you're starting | It runs off a briefing that is already in your inbox at 7:30, built from the past week's threads and calls, not reconstructed from memory. |
| DIBS | It stays a separate, gated domain. Nothing from DIBS enters the deal graph until you write the rule that lets it. |
| Founder-only access | It stays founder-only. When someone joins, they see only what their role allows, enforced in the store rather than by trust. |

**Next step:** create the Day AI workspace at [day.ai/login](https://day.ai/login).
That requires one Professional Agent at $75/month, cancel anytime; teammates,
data and chat are free. Use coupon code **`UPGRADEMYBRAIN`** at checkout for a
free first month. Then come back to this repo in Claude Code and say so; the
build starts from section 7 of this document. Section 9 has the details.

---

## 2. Current state

### Inventory (surveyed October 3, 2026)

| What | Evidence | Status |
| --- | --- | --- |
| Repo | `dibs-financial/cornerstone-creative-capital-`: one commit (`b984025`, Initial commit), one contributor | Exists, empty |
| Files | `README.md`, containing the title line only | No knowledge content |
| Rules for agents (`CLAUDE.md`, `BRAIN.md`) | none | Missing |
| Skills / agents (`.claude/skills/`, `.claude/agents/`, prompt libraries) | none | Missing |
| Automation (cron jobs, GitHub Actions, webhooks, `package.json`) | none | Missing |
| Memory layer (databases, exports, CSVs) | none | Missing |
| Email | Gmail / Google Workspace (from you) | In use, not connected to any brain |
| CRM | none (from you) | Not needed: founder, no legacy CRM |
| Meeting recorder | none (from you) | Missing |
| Slack | not in use (from you) | Out of scope |
| Product / engineering tracker | not applicable to the lending business | Out of scope |

### Against the seven-layer reference shape

| Layer | Present? | What it means for Cornerstone |
| --- | --- | --- |
| 1. Constitution (`company/`) | No | Who you lend to, the loan products (EMD, gap), the rules that are never broken |
| 2. Domains (`domains/`) | No | Lending, escrow and title partners, borrowers, DIBS |
| 3. Decisions (`decisions/`) | No | Dated rules with what they replaced. Rule 1 is the first |
| 4. Current state (`state/`) | No | This week's pipeline, priorities, risks |
| 5. Procedures (`skills/`) | No | Triage, underwriting checklist, wire check, Monday review |
| 6. Source registry (`sources/`) | No | Which system holds the truth for each fact (Gmail for status, escrow for wire receipt) |
| 7. Governance (`governance/`) | No | Data classification, what agents may draft versus do |

### Ladder rung

**Below rung 1.** Rung 1 is a model plus connectors. You use AI tools, but
nothing here connects them to Cornerstone's data yet.

### Honest strengths

- **Nothing to unlearn.** No CRM full of stale stages, no export jobs, no
  rules that contradict each other. Every definition in section 7 is written
  once, correctly, before any data arrives. That's the order that works, and
  most teams can only get to it by migrating.
- **A business rule that's already crisp.** "Funds go only to escrow, always"
  is exactly the kind of rule an agent can enforce. It's specific, testable,
  and it protects against the most expensive failure in your business.
- **A one-number goal.** Deals funded, with a target of 10 in 90 days, gives
  every skill a bar to clear and the evaluation a judge (you) and a date.
- **One mailbox.** Your whole deal flow passes through one Gmail account
  today, so connecting a single source captures most of the business.
- **You are the builder.** The biggest risk in adoption is a team with seats
  and nobody writing skills. That isn't your problem.

**The one-person caveat, stated kindly:** this is a single-hero system by
design right now. That's fine for 90 days. It also means the brain's first job
is to hold what's in your head (terms, partners, deal status), so the business
doesn't stop if you're out for a week.

---

## 3. Definition of success

Agreed in this session on October 3, 2026, in your words:

- **Business outcome:** deals funded. **10 deals funded in 90 days**
  (Oct 3 → Dec 31, 2026).
- **Security and compliance:** founder-only access for now. Access rules are
  written before anyone else is added.
- **Adoption:** "I need one": a weekly deal review, which doesn't exist today.
  It will be **every Monday**, run by you off an agent briefing.
- **Better answers:** current terms and deal status, cited, never a replaced
  rule.
- **Standing rule:** "Fund money only goes to escrow. Always."

What Cornerstone is, in your words: *"a lender-facing LLC that provides EMD
loans & Gap Funding. It also owns DIBS (Decentralized Infinite Bank-like
System)."*

---

## 4. The bar

Every aspect below is graded against four requirements. A brain that misses
one of them is a prototype, not a finished brain.

1. **Safety.** Permissions are enforced in the store, per person. Ingestion is
   governed by explicit inclusion *and* exclusion rules. Credentials are per
   person, never one shared all-access login. Every value has a traceable
   source, and a source can be purged along with everything derived from it.
   For Cornerstone in particular, this covers borrower personal and financial
   data and wire instructions.
2. **Performance.** Data lands continuously, within minutes, not on a nightly
   job. It's kept at full fidelity: whole threads and whole transcripts, not
   summaries. Retrieval is fast and cheap enough for an agent to brief you on a
   deal in seconds.
3. **Capability.** Things can fire when data arrives, such as an email or a
   recording becoming ready, not only on a timer. Deals and actions are created
   and updated from the source material automatically. Every source sits in one
   graph tied to the same borrowers, escrow companies and deals.
4. **Adoption.** It covers the whole team's data and use, once there is a
   team. People can talk back, and the agent changes. It adds **no data
   entry**: the upgrade removes typing and never adds it.

---

## 5. Findings by aspect

Five aspects were evaluated. Slack and product/engineering are out of scope:
you don't use Slack, and Cornerstone doesn't ship software through a tracker.
CRM is covered briefly because "no CRM" is itself a finding. Meetings and email
carry the plan.

### Email

**What you use:** Gmail on Google Workspace, one mailbox (founder). This
mailbox carries borrower requests, purchase contracts, escrow-officer
correspondence, title commitments, wire instructions and payoff
correspondence.

**Captured in the company brain today:** nothing. Every deal's status lives in
the inbox and in your head.

**What's lost without it, in your world:**
- A borrower's 4:10pm reply ("seller accepted, need EMD by tomorrow noon") sits
  unread until you next check. Speed is the product in EMD lending.
- Wire instructions arrive by email, and email is where wire fraud happens. No
  system compares an incoming instruction with the escrow company already on
  file for that deal.
- Payoff dates live in threads. Nothing reminds you that a gap loan is due on
  closing day, or that a closing slipped.
- "What are our terms?" has no single current answer, so an old quote in a
  six-month-old thread can be mistaken for today's.

**Grade against the bar:**

| Requirement | Today | Gap |
| --- | --- | --- |
| Safety | Gmail's own security only. There are no classification or exclusion rules, and no wire check | Exclusion rules (personal mail, DIBS, regulated borrower documents); Rule 1 checked on every wire email; a traceable source for every deal fact |
| Performance | Nothing is ingested | Threads in the graph within minutes, whole threads with attachments referenced |
| Capability | Nothing fires | An incoming request creates a deal and drafts a reply; an incoming wire email triggers the check |
| Adoption | You re-read threads to rebuild status | Status comes out of the email itself. You type nothing to keep the pipeline current |

**Ideal outcome:** your mailbox flows into the graph continuously. Each thread
resolves to a borrower, an escrow or title company, and a deal. Personal mail,
DIBS mail and borrower identity and bank documents are excluded by rule.
Incoming requests and wire instructions fire skills. When a teammate joins,
they see only the threads their role allows.

**DIY path (honest):**
- *Solo, read-only, on demand: feasible now.* Claude Code with a Gmail
  connector can search and read your mailbox when you ask. Pair it with a
  `deals/` folder of one Markdown file per deal, which a skill updates when you
  run it. Effort: a few days. Limits: it only runs when you open the laptop, so
  nothing fires on arrival. Status is a copy in Markdown that drifts from the
  inbox. Provenance is whatever the skill remembers to cite.
- *Continuous ingestion: hard.* It requires the Gmail API with restricted
  scopes, push notifications or polling, a store, thread-to-deal matching, and
  handling for Gmail's undocumented rate limits. Hitting those limits can
  suspend API access to your own mailbox for an unknown period, which is
  dangerous for a business that runs on that inbox. Effort: weeks, and then you
  maintain it.
- *Governance and multi-person permissions: not a reasonable build.*
  Inclusion and exclusion by address, domain and label, per-thread
  authorization, and purge by lineage are a product, not a weekend. They don't
  matter while you are alone; they become required the day a second person
  has access.

**With Day AI:** Google Workspace connects under your own login. Inclusion and
exclusion controls by address, domain and label, per-thread permissions, and
continuous ingestion come built in. Threads resolve to people, organizations
and opportunities, and an email arriving can trigger a skill. *Verify in a
demo (section 10): handling of PDF attachments such as title commitments and
wire letters, and the exclusion controls for borrower identity documents.*

**Sequence:** step 3 of section 7, right after the rules are written and the
recorder is turned on. For Cornerstone it is the highest-value source, because
the deal flow *is* email.

### Meeting recording

**What you use:** no recorder. Calls with borrowers, wholesalers, escrow
officers and capital partners happen with no record. *Open: the mix of phone
versus Zoom/Meet calls, and how many per week (section 10).*

**Captured in the company brain today:** nothing. Everything said on a call
disappears when it ends, unless you write it down.

**What's lost without it:** a borrower's stated exit ("assignment closes the
14th, I'm paying you from the assignment fee") and an escrow officer's verbal
confirmation of the account. Also the terms you quoted, which is the commitment
you will be held to. Calls are where the facts behind underwriting are said
first.

**Grade against the bar:**

| Requirement | Today | Gap |
| --- | --- | --- |
| Safety | No record, which is also no evidence | Consent-compliant recording, with the transcript attached to the deal |
| Performance | Nothing is captured | Full transcript within minutes of the call ending |
| Capability | Nothing fires | A recording becoming ready updates the deal and drafts the follow-up |
| Adoption | You take notes, or don't | You do nothing different and the record exists |

**Ideal outcome:** every video call about a deal is recorded with consent,
transcribed, and attached to the deal. The follow-up email is drafted from the
transcript, including the terms quoted. Phone calls are covered either by
moving deal calls to Meet or Zoom, or by a one-line voice note logged after
the call.

**DIY path (honest):** a recording bot per platform, consent notices by
state, storage, transcription, matching speakers to contacts, then plumbing
transcripts into the deal files. That's months of work to end up worse than an
off-the-shelf recorder. A lighter DIY option is a commercial recorder plus a
skill that pulls its transcripts. That works, but the transcripts live in a
second silo.

**With Day AI:** per Day AI, the recorder is native and free, consent-handled,
and lands transcripts in the same graph as email, tied to the deal. A
recording becoming ready can fire a skill directly. *Verify in a demo: phone
calls are likely not covered, so confirm which platforms are.*

**Sequence:** step 2 of section 7. It's free, quick to turn on, and the least
sensitive source. Within email-first lending its value comes second to email,
but it goes live first because it costs nothing and gets used right away.

### CRM

**What you use:** none. **Finding: this is an advantage.** There's nothing to
migrate, so no field mapping and no stale stages. A legacy CRM would make you
type data in by hand, the opposite of the "no data entry" requirement.

**Grade against the bar:** not applicable. The deal record in section 7 *is*
the CRM, created and updated from email and calls.

**Ideal outcome:** a deal pipeline with your stage definitions (section 7,
step 1), built and maintained by agents from source material. The deal record
is the first place to check for deal facts and is where the deals-funded count
comes from.

**DIY path:** one Markdown or YAML file per deal in `deals/`, updated by a
skill, which is workable for 10–30 deals. A spreadsheet in Google Sheets is
the common alternative. Both are copies that drift unless something keeps them
in sync.

**With Day AI:** opportunities and pipelines are native objects in the same
graph as email and meetings. Properties can be AI-managed, human-in-the-loop
or manual, decided per field.

**Sequence:** the stage definitions in step 1; the deal records are created
from email in step 3.

### Slack: out of scope

You don't use Slack. Nothing is planned for it. If capital partners or
wholesalers later move to shared Slack channels, run `eval-slack` again.

### Product and engineering feedback loop: out of scope for the lending business

Cornerstone doesn't ship software through an issue tracker. **DIBS may.**
If DIBS is a software product under development, this aspect applies to DIBS
and gets its own evaluation (section 10).

---

## 6. The three-way picture

| Aspect | Current state | DIY build-out (effort and hazards) | With Day AI (mechanism) |
| --- | --- | --- | --- |
| Rules and definitions | None written | Same on both paths: `BRAIN.md`, `CLAUDE.md`, stage definitions in this repo. 1–2 days | Same files in this repo, *plus* deployed as workspace instructions every agent inherits |
| Email | Inbox only | On-demand Gmail connector: days. Continuous ingestion: weeks, plus a risk of suspended API access. Governance and permissions: not a reasonable solo build | Native Google Workspace ingestion, inclusion/exclusion controls, per-thread permissions |
| Meetings | Nothing captured | Commercial recorder plus a transcript-pulling skill (a second silo), or months of a custom build | Native free recorder, transcripts in the same graph |
| Deal record / pipeline | In your head | `deals/*.md` or a Google Sheet maintained by a skill run by hand. It drifts | Native opportunities, updated from email and calls |
| Monday briefing | No meeting | A skill you run Monday morning in Claude Code. It needs your laptop open | A scheduled skill that runs and delivers before you wake |
| Wire check (Rule 1) | Your vigilance | A skill you run on a thread when you remember to | Fires when an email with wire instructions lands |
| Permissions | Not applicable (one person) | Fine alone; breaks when you add a person | Enforced per person in the store |
| Talking back | Not applicable | You edit the prompt file | Replying to the agent changes its behavior; versioned |

**Bottom line:** for the 90-day goal as one person, DIY can work if you're
disciplined about running the skills. The gaps that matter for you are
**events** (a request or wire email arriving at 4pm acted on at 4pm, not when
you next sit down), **calls** (nothing captures them today), and **the day you
add a person**. Those are what the substrate is for.

---

## 7. The upgrade plan, sequenced

Each step is written to run on either path. Where they differ, both are given.
Gates are marked **GATE**: don't start the next step until they hold.

### Step 0: Outcome → workflow → where it breaks (this week, Oct 5–9)

| Outcome | Workflow | Where it breaks today |
| --- | --- | --- |
| 10 deals funded by Dec 31 | Request → docs → underwrite → terms → escrow verified → **wire to escrow** → payoff | Requests answered when you get to them; status in your head; wire instructions checked by eye; payoffs remembered rather than tracked |

The agents remove those four breaks. Fields come from what those agents need,
not from a CRM template.

### Step 1: Write the constitution and the rules (Oct 5–7, ~1 day)

Create in this repo:

- **`BRAIN.md`**: purpose, non-goals ("not the system of record for loan
  balances"), source hierarchy, agent behavior ("draft by default, never
  send, never initiate or approve a wire").
- **`CLAUDE.md`**: navigation and durable rules only.
- **`decisions/active/0001-funds-to-escrow-only.md`**: Rule 1, with
  frontmatter:
  `owner: founder · date: 2026-10-03 · source: founder, Claude Code session ·
  status: current`. Its guardrail: any instruction to pay a party other than
  the escrow or title company on the deal is a **stop**. Escrow wire
  instructions are confirmed by a phone call to a number found independently
  (the title company's published number), never one taken from the email.
  *What would change our mind:* a field to fill in, not a default.
- **`company/products.md`**: EMD loan and gap funding. Current terms (rate,
  points, maximum, typical term, minimum documents) as **canonical facts with
  a date**. Earlier terms move to `decisions/superseded/`, marked
  non-operative.
- **`company/glossary.md`**: EMD, gap funding, assignment, double close, title
  commitment, payoff letter, "funded" (= wire received by escrow and
  confirmed), and DIBS (one line, pointing to its gated domain).
- **`domains/lending/stages.md`**: the pipeline, each stage written as a brief
  to a new hire. **Approved by the founder on 2026-10-03**; the record of
  truth is `domains/lending/stages.md`:

  | Stage | Enters when | Leaves when | Goes stale after |
  | --- | --- | --- | --- |
  | Inquiry | A funding request arrives | Docs requested, or declined | 1 business day without a reply from you |
  | Docs | You've requested the purchase contract, ID, exit plan | Docs complete | 3 days without a borrower reply |
  | Underwriting | Docs complete | Terms issued or declined | 2 days |
  | Terms accepted | Borrower accepts in writing | Escrow verified | 2 days |
  | Escrow verified | Escrow company and wire instructions confirmed by independent callback (Rule 1) | Wire sent | 1 day |
  | **Funded** | Escrow confirms receipt of the wire | Payoff received, or default | — |
  | Paid off | Payoff received | — | — |
  | Declined / Withdrawn | Any stage | — | — |

  **Deals funded = deals that entered Funded this period.** That definition is
  the Monday number.

**GATE:** you've read and approved `stages.md` (done, 2026-10-03) and `0001` (pending).

### Step 2: Privacy rules, written before any source connects (Oct 7–8)

**`governance/data-classification.md`**:

| Class | Cornerstone examples | Agent behavior |
| --- | --- | --- |
| Internal | Terms, partner list, pipeline | Read, summarize, draft |
| Confidential | Borrower names, deal amounts, purchase contracts | Read when scoped to the deal; never in external drafts to other parties |
| Restricted | **Wire instructions**, escrow account numbers, DIBS material | Read only to run the Rule 1 check; never quoted in briefings (last 4 digits only) |
| Regulated | Borrower SSNs, ID scans, bank statements, credit reports | **Excluded from the brain.** They stay in Gmail or your document vault. The brain records "received, date," never the content |

**`governance/ingestion-rules.md`**: include your business address and
business threads. Exclude personal domains and family, banking and brokerage
notification senders, anything labeled `Personal` or `DIBS`, and attachments
matching ID, bank-statement or credit-report patterns.

**`governance/agent-action-policy.md`**: read is wide; draft is strong;
**send is never unsupervised**. Agents **never** initiate, approve or
change a wire. They don't change terms. Marking a deal Funded needs your
confirmation.

**Account hygiene (both paths, do this regardless):** hardware-key or
app-based two-factor on the Google account, and a review of mail forwarding
rules. A compromised inbox is the main way wire fraud starts.

**GATE:** written and committed before step 3.

### Step 3: Connect sources, highest trust-to-value first (Oct 8–10)

1. **Meeting recorder** (Day AI: free; DIY: a commercial recorder). Turn it on
   for Meet and Zoom calendar events. Move deal calls to video where you can.
   For phone calls, a 20-second voice memo or a typed note to yourself by
   email ("Call w/ [borrower], exit = assignment 10/14") is the fallback, and
   it goes through the email path.
2. **Gmail and Calendar**, under your own login, with the step 2 rules
   applied. **Backfill 90 days** so open deals and recent payoffs exist on
   day one.
3. **Source registry** (`sources/canonical-sources.yaml`): deal status comes
   from the deal record (derived from email); terms from `company/products.md`;
   wire receipt from **escrow's confirmation email only**; loan balance from
   your bank or ledger (never copied into Markdown).

**GATE (data readiness):** the backfill created a deal record for every deal
you know is open, and you've spot-checked five of them against your memory.
If one is wrong, fix the matching rules before any skill reads them.

### Step 4: The fleet, one workhorse plus one background skill (Oct 10–12)

**One agent: `Cornerstone Deal Desk`.** It has one job: keep every funding
request moving toward funded or a clean decline, and protect every wire.
Owner: you.

| Skill | Situation it serves | Trigger | Bar (numeric) | Empty case | Acts by |
| --- | --- | --- | --- | --- | --- |
| **`monday-deal-review`** | Monday 8:00 deal review | Cron, Mon 7:30 CT | Deals funded this period vs. the target of 10 and the weekly pace needed; every deal in Docs, Underwriting, Terms accepted or Escrow verified listed with its next step and owner; every payoff due in 14 days | "No open deals and no payoffs due. Pace needed: N per week." One line | Email to you; ≤1 screen on a phone |
| **`new-request-triage`** | A borrower or wholesaler asks for EMD or gap money | Email lands from a new sender with funding language | Deal record created and a docs-request reply drafted within 5 min of arrival | No funding language: does nothing | Draft in Gmail, unsent |
| **`wire-instruction-check`** (Rule 1) | An email contains wire or bank instructions | Email lands with routing or account patterns, or an attached wire letter | Every such email checked: is the payee the escrow or title company on this deal? Do the instructions match ones previously verified? | Not wire-related: silent | Flag to you marked **STOP** on any mismatch or change; never edits, never forwards |
| **`deal-record-keeper`** (background) | Status moves when emails and calls happen | Each email or recording on a deal | Stage and next step updated, with the source thread cited; old → new reported with date | No change: silent | Writes the deal record; Funded needs your confirmation |

Skill-writing standard for all four: section headings named after situations,
not systems. Each has a numeric bar, an explicit empty case, and a list of
things it never does. It names its sibling skills so they don't overlap.

**DIY version:** the same four skills as `.claude/skills/*/SKILL.md`, run by
hand or from a local scheduler. `new-request-triage` and
`wire-instruction-check` become "run on my inbox when I sit down": the
on-arrival protection is lost. **Day AI version:** the same prompts, written
here and deployed over MCP. They fire on the email event and on the Monday
schedule.

### Step 5: Ignition plan

- **The standing meeting:** **the Monday deal review**, every Monday,
  8:00–8:30 CT, on your calendar starting **Monday, October 12, 2026**.
  It's the meeting you said you need.
- **The leader's number from the agent:** *deals funded vs. 10.* You
  quote it from the briefing, not from memory. If the two disagree, the
  briefing is wrong and gets fixed that day.
- **Owner of the managed skills:** you.
- **Crawl → walk → run:**
  - **Crawl (Oct 12 – Oct 25):** briefing and triage drafts, human-in-the-loop
    on everything. Wire check flags only. **Two-week test (Oct 26):** did you
    run two Monday reviews off the briefing, and did it list every open deal?
  - **Walk (Oct 26 – Nov 22):** `deal-record-keeper` writes stages
    on its own (except Funded). You start replying to the agent ("shorter,"
    "skip payoffs > 30 days") and the skills change.
  - **Run (Nov 23 – Dec 31):** add a payoff-watch skill (daily, payoffs due in
    3 days and slipped closings) and a post-call follow-up drafted from the
    transcript. Decide on DIBS and any first teammate (step 6).
- **Success bar:** **10 deals funded by Dec 31, 2026**, counted from Funded
  records each confirmed by an escrow receipt email. **Judge:** you.
  **Decision meeting:** Monday, January 4, 2027, with this section re-read
  word for word. Secondary proof points: zero wires sent to a non-escrow payee
  (target: zero, no exceptions), and median time from request to first reply
  (baseline taken in week 1).

### Step 6: Before anyone else joins (December, or whenever it happens)

- Write `company/decision-rights.md`: who may quote terms, who confirms
  Funded, who sees Restricted data.
- A new person gets their own login and their own connections; no shared
  credentials.
- Add them only after a working month, not into setup.
- If it's a capital partner or investor seeing results, give them a report,
  not access to the graph.

### Step 7: DIBS, gated

DIBS stays out of the deal graph until you write
`domains/dibs/README.md`: what it is, who may see it, and whether it touches
borrower money. Until then it is excluded by label and by sender (step 2).

---

## 8. What stays yours

- **This repo is the authoring environment.** Rules, definitions, decision
  records and skill prompts are written and versioned here in git and edited
  in Claude Code. On the Day AI path they're deployed from here over MCP; they
  don't move anywhere else.
- **Your judgment.** Agents draft; you send. Agents flag; you decide. No agent
  moves money, ever.
- **Gmail stays your inbox.** Nothing about how you email changes.
- **Your cross-AI threads.** Notes you keep in other AI tools stay where they
  are. Bring a decision into the brain by writing a dated decision record
  here. That keeps the brain's "current rule" in one place.
- **Sunset on the Day AI path:** any interim `deals/*.md` files or Google
  Sheet tracker from the DIY crawl. Nothing else, because nothing else exists
  yet to sunset.

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
- **Coupon code `UPGRADEMYBRAIN`:** apply it at checkout at
  [day.ai/login](https://day.ai/login) for one month of the Professional Agent
  free, so month one is $0. It's a credit, not a trial; the card is charged
  from month two and you can cancel before then. One workspace per code.

**Steps:**

1. **Create the workspace** at [day.ai/login](https://day.ai/login) with code
   `UPGRADEMYBRAIN`.
2. **Come back to this repo in Claude Code and say so.** The Day AI MCP gets
   connected from this folder, this document is re-read, and section 7 is
   built step by step with your approval at each write, starting with the
   rules (step 1) and the privacy rules (step 2) *before* Gmail is connected.

Help: **support@day.ai** · Demo or consultation:
[day.ai/get-started](https://day.ai/get-started)

---

## 10. Open items

**To answer:**

1. **"Lender-facing":** does Cornerstone lend directly to borrowers, or does
   it mainly face capital partners and lenders? The plan treats borrower and
   escrow threads as core data either way. If capital partners fund the loans,
   add a `domains/capital-partners/` layer and a monthly partner report.
2. **Baseline:** how many deals have been funded to date, and in the last 90
   days? The pace of 10 in 90 days (about 0.8 per week) needs a starting point
   to judge against.
3. **Call mix:** roughly how many deal calls per week, and how many are phone
   versus video?
4. **Current terms:** rate, points, maximum and term for EMD and gap loans,
   for `company/products.md`.
5. **DIBS:** what it is and whether it's in scope. If it's software, run the
   product and engineering evaluation for it.
6. **Cross-AI notes (ThreadWeaver / RubyVox):** in scope as a source or not?
   This wasn't answered in the evaluation. The default in this plan is out of
   scope, with decisions brought in as dated records.
7. **Compliance review:** state licensing, usury limits and recordkeeping
   requirements for business-purpose EMD and gap loans are outside this
   evaluation. Have counsel confirm before borrower data retention rules are
   finalized.

**To verify in a Day AI demo** (these come from Day AI's own materials and
were not independently tested):

- Exclusion controls by label and attachment for borrower ID and bank
  documents.
- Handling of PDF attachments (title commitments, wire letters) for the
  Rule 1 check.
- Recorder coverage for phone calls versus Meet/Zoom, and consent handling in
  your state.
- Whether a skill can trigger on an incoming email matching a pattern (needed
  for `wire-instruction-check` to fire on arrival).
- Export: whether you can take your deal records and transcripts out if you
  leave.
