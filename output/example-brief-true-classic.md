# Account research brief — True Classic (worked example)

**This is an illustrative worked example, not a real pipeline run.** No
outbound pipeline exists yet — Orderful has no engagement with John, and
`ingest/`/`enrich/`/`score/` have no actual code. This exists to show what
`../templates/account-research-brief.md` filled in for a real, verifiable
company would look like, following the process in
`../skills/account-research-skill.md`. Built 2026-09-17 from public sources
only. True Classic has no relationship with John or this repo and hasn't
been contacted — nothing below should be read as outreach that happened.

## Company basics

- **Name:** True Classic (menswear/apparel)
- **Founded:** 2019, by Ryan Bartlett, Nick Ventura, and Matthew Winnick
- **HQ:** Glendale, CA
- **Size:** ~162 employees (per third-party company-data aggregators —
  precision unconfirmed, treat as approximate); reported ~$500M revenue,
  ~$850M valuation after its first outside investment (1686 Partners)
- **Website:** trueclassic.com
- **Sources:** [PitchBook](https://pitchbook.com/profiles/company/452765-53),
  [WWD](https://wwd.com/menswear-news/mens-sportswear/true-classic-mens-t-shirts-target-ben-yahalom-1236762306/),
  [RetailWire](https://retailwire.com/true-classic-partners-target-t-shirts/)

## Signal(s) that triggered this

**Tier 1 — new major-retailer launch** (signal #1 in
`../onboarding/signal-inventory-template.md`). True Classic launched in 460
Target stores nationwide (2026), after first testing a small T-shirt
selection on Target.com starting in October — a real, dated go-to-market
event, not a rumor. CEO Ben Yahalom has publicly said the partnership "has
potential to grow" pending initial response, meaning further Target expansion
(more stores, more SKUs) is plausible, not a one-time event. Source:
[RetailWire](https://retailwire.com/true-classic-partners-target-t-shirts/),
[Retail Dive](https://www.retaildive.com/news/true-classic-launches-at-target/735624/).

## ICP fit check

Against `../onboarding/icp-template.md`:

- **Industry/company type:** direct match — a consumer/DTC brand moving
  further into big-box wholesale distribution. **2/2**
- **Size/trading-partner band:** True Classic is described as already "a
  major wholesale player" beyond just this Target launch — meaning it's
  likely *not* a first-time EDI buyer, but a company scaling trading-partner
  count across several retail relationships at once, which is arguably a
  stronger fit than a true EDI first-timer (matches Orderful's own stated
  pain point of "growth friction" and "cannot handle scale" — see
  `../onboarding/company-understanding-inventory.md`). **2/2**
- **Geography:** US-based, North America. **2/2**
- **Disqualifiers:** none identified. No evidence of being contractually
  locked to a competitor with no visible pain, no evidence of exclusively
  staying DTC (actively expanding wholesale), no known scope mismatch.

**Fit score: 6/6 (High)** — see `../score/scoring-model.md`.

## Persona mapping

Maps to **"Ops/Systems lead at a consumer brand entering retail"**
(`../onboarding/persona-template.md`) — the pattern this persona is built
from (Liquid Death's "Business Applications Manager") is the same shape of
company as True Classic: a DTC-first consumer brand where an operations/
supply-chain/business-systems function, not a large dedicated IT department,
most likely owns retail-partner integration work.

**Named contact: unconfirmed.** No specific person identified — would need an
actual enrichment step (e.g. a LinkedIn search for "Operations," "Supply
Chain," or "Business Systems" titles at True Classic) that hasn't been run.
Not guessed at.

## Prior relationship check

**No relationship found.** True Classic does not appear among Orderful's
public customer logos or case studies (`../onboarding/company-understanding-inventory.md`'s
"Current customers" section) — genuinely new, as far as public information
shows. (Contrast with Caraway, which *is* a named Orderful customer and
shows up in the same kind of Target/Walmart-launch story — used elsewhere in
this repo as validation that the signal pattern is real, not as a prospect.)

## Recent public activity

- Target launch itself (460 stores, Short Sleeve Classic Crew tees,
  $29.99-$99.99 price points) — the signal.
- Already operates 9 of its own retail locations and has "become a major
  wholesale player" per WWD — suggests active, multi-partner retail
  operations already underway, not a single new relationship in isolation.
- First outside institutional investment (1686 Partners) after bootstrapping
  to nine-figure revenue — a company recently added outside capital and
  investor expectations, plausibly accelerating expansion pace.

## Client-specific research priorities (per `../templates/account-research-brief.md`)

- Whether this is True Classic's *first* EDI-requiring retail relationship or
  one of several — **appears to be the latter** ("major wholesale player"
  already), which changes the pitch from "get EDI-compliant for the first
  time" to "your EDI setup is about to get tested at a new scale."
  Unconfirmed which vendor (if any) currently handles this for them.
- Whether Target's Perfect Order Program (signal #2's compliance-change
  trigger) applies to True Classic specifically — plausible given they're
  now a Target supplier, but not separately confirmed; would be a strong
  second signal to stack if verified (see scoring model's stacking bonus).

## Score (per `../score/scoring-model.md`)

- **Fit: 6/6 (High)**
- **Intent: Tier 1 signal fired = 3 points (High)**
- **Combined tier: Hot**

## Resulting draft outreach

This is **Template 1** from
[`../templates/outreach-templates.md`](../templates/outreach-templates.md)
(consumer brand ops lead × new retailer launch) with its variables filled in
from the confirmed facts above — not a bespoke message written just for this
account. Per `business.yaml`'s `outbound_send: draft_only`, this is a draft
for human review and sending, not something sent automatically.

| Variable | Value used | Source |
|---|---|---|
| `{{contact_first_name}}` | *unconfirmed — see Persona mapping* | n/a |
| `{{company_name}}` | True Classic | Company basics |
| `{{retailer_name}}` | Target | Signal |
| `{{signal_detail}}` | the 460-store Target rollout, after first testing on Target.com in October | Signal / Recent activity |
| `{{proof_point}}` | Liquid Death and Caraway, who've used Orderful to onboard new retail partners in days instead of months without adding headcount | `../onboarding/company-understanding-inventory.md` |
| `{{sender_name}}` | *n/a — set at send time* | n/a |

> **Subject:** Congrats on the Target launch — a question on scaling it
>
> Hi [Name] — saw the 460-store Target rollout, after first testing on
> Target.com back in October — congrats, that's a real step up.
>
> Curious how EDI is holding up as Target scales alongside whatever other
> wholesale partners True Classic runs today. We work with brands in a
> similar spot (Liquid Death, Caraway) who've used Orderful to connect once
> and onboard new retail partners in days instead of months, without adding
> headcount for it.
>
> Worth 15 minutes to see if there's a gap between where your EDI setup is
> today and where Target's volume is about to take it?
>
> [Sender name]

The unresolved `{{contact_first_name}}` and `{{sender_name}}` variables are
left as `[Name]` / `[Sender name]` rather than invented — per
`outreach-templates.md`'s own rule, an unconfirmed variable doesn't get
guessed at just to make the draft read as more finished than the research
actually is.
