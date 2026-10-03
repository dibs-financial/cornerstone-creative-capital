---
id: ingestion-rules
status: draft
owner: founder
date: 2026-10-03
review_by: 2027-01-04
applies_to: Gmail, Google Calendar, meeting recorder — every source, before it connects
related: [governance/data-classification.md]
---

# Ingestion rules

What enters the brain, and what never does. Written **before** any source
connects. Exclusion always beats inclusion: if a thread matches both, it stays
out.

## Gmail — founder's mailbox

The founder's mailbox mixes business and personal mail, so ingestion is
**inclusion-first**: a thread enters only if it matches an inclusion rule
and no exclusion rule.

### Include

| Rule | Type | Value |
| --- | --- | --- |
| I-1 | Label | `Cornerstone` — anything the founder labels this |
| I-2 | Domain | Escrow and title companies on file — *list below* |
| I-3 | Domain / address | Private money lenders (PMLs) and other capital partners: business domains in `partner_domains` below; individual personal-provider addresses (Gmail, Yahoo, etc.) matched against the **PML list**, held in the brain and never committed here |
| I-3b | Address | Repeat borrowers and wholesalers on file — *list below* |
| I-4 | Content | New senders whose message asks for EMD, earnest money, gap funding, or a loan for a property purchase (feeds `new-request-triage`) |
| I-5 | Content | Any message containing wire, routing, or account instructions (feeds `wire-instruction-check`; handled as Restricted) |
| I-6 | Thread | Every reply in a thread that was already included |

### Exclude (always wins)

| Rule | Type | Value |
| --- | --- | --- |
| X-1 | Label | `Personal` |
| X-2 | Label | `DIBS` — until `domains/dibs/README.md` says otherwise |
| X-3 | Label | `Legal` — counsel correspondence stays out |
| X-4 | Address | Personal contacts and family — *list below*. Never exclude a whole personal-provider domain (gmail.com etc.): half the PML list uses one |
| X-5 | Sender type | Bank, brokerage, card, and payment-app notifications (statements, alerts, 2FA codes) |
| X-6 | Sender type | Newsletters, marketing, receipts, social media |
| X-7 | Attachment | Borrower ID scans, bank statements, credit reports, tax returns (Regulated). The thread may enter; **the attachment content does not** |
| X-8 | Content | Messages containing an SSN pattern — thread excluded until the founder reviews |

### Lists (founder fills in)

```yaml
escrow_and_title_domains: []    # e.g. sometitle.com
partner_domains:                # PML business domains — source: PML-lenders-for-bots.csv (185 lenders, 2026-10-03)
  - 3dcapital.me
  - 4ksconsulting.com
  - abetterconnecter.com
  - aethersmithventures.com
  - alliancesquad.com
  - ambenterprisegroup.com
  - ampmgroupenterprisellc.com
  - arrowheadcapitalfunding.com
  - axiominvesting.us
  - bartsbucks.com
  - bhcreatorsolutions.com
  - boomerangair.com
  - bridgetoscale.com
  - brollyjv.com
  - campbellridgehomes.com
  - centerfieldventuresllc.com
  - chatcyreale.com
  - chimbacapital.com
  - cmventuresolutions.com
  - consultwithbeacon.com
  - creativecashpartners.com
  - creativedealfunding.com
  - ekconsultinggroupllc.com
  - emeraldhavenllc.com
  - ereinnovativesolutions.com
  - evergreeninvestorloans.com
  - ferocityassets.com
  - financemydeals.com
  - fuelmydeal.com
  - fundflowing.com
  - fundmyrei.com
  - gallagher.capital
  - getfunds2invest.com
  - gpm101.com
  - grabagator.com
  - gtr7consulting.com
  - ibnconsultingllc.com
  - iipva.com
  - ironheartproperties.com
  - jakgi.com
  - kaboomventures.com
  - kopdynamicsolutions.com
  - legacycapitalresources.net
  - lifecyclerealty.com
  - lionwoodventures.com
  - madrygacapital.com
  - mareisolutions.com
  - marmcreativesolutions.com
  - merqavaventures.com
  - michelleshomesolutions.com
  - mightybullfunding.com
  - milehiprop.com
  - mkdcapitalventures.com
  - motheinvestor.com
  - mountainmoverinvestments.com
  - multyfunds.com
  - myinvestorloan.online
  - nightlightsolutions.com
  - nurturedcapitalsolutions.com
  - nxtlevelfinance.com
  - pbnjinvestors.com
  - peachstatecapital.com
  - pearlcreekproperties.com
  - property52.com
  - qrein.com
  - qslholdings.com
  - realresultsrealtyinc.com
  - redarrowmanagement.com
  - relationalcapital.com
  - restoration-north.com
  - rfsfunding.com
  - rocketcap.co
  - rwcholdings.com
  - saltandsoilproperties.com
  - silverliningmt.com
  - southerngrowthllc.com
  - sunrise.properties
  - symbiosellc.com
  - t2omni.com
  - tdjmanagementsolutions.com
  - theboutin.com
  - thegapinvestors.com
  - thetc-collective.com
  - threeamcapital.com
  - ts-aristocrat.com
  - ullend.com
  - vernoncreativeconsulting.com
  - vhsfunding.com
  - vhsrealestate.com
  - vikingprop.com
  - vmopartners.com
  - wjsegroup.com
pml_personal_addresses: see PML list in the brain   # 92 addresses on gmail.com, yahoo.com, etc. — Confidential, never in this repo
known_borrowers: []             # repeat borrowers / wholesalers
personal_exclusions: []         # family, friends, personal services
```

### Backfill

90 days at first connection, with these rules applied. No earlier history
unless the founder asks for a specific deal.

## Google Calendar

- Include: events with an included contact, or with "EMD", "gap",
  "closing", "payoff", or a property address in the title.
- Exclude: events marked private, and all-day personal events.

## Meeting recorder

- Record: video calls (Meet/Zoom/Teams) with an included contact, and the
  founder's own deal-review meeting.
- Never record: calls with counsel, personal calls, DIBS calls.
- Consent notice on every recorded call. Check whether your state requires
  everyone's consent before recording, and set the recorder to match.
- Phone calls are not recorded; log them with a short note to self, which
  enters through I-1.

## Changing these rules

Edit this file, commit, and note the date. New rules apply going forward; if an
exclusion is added, purge anything it would have excluded
(`data-classification.md`, rule 4).
