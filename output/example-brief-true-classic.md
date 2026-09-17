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

**Score is Hot (see below), so per `../onboarding/persona-template.md`'s
multi-threading section, this brief maps two contacts, not one.**

**Primary — "Ops/Systems lead at a consumer brand entering retail"**
(`../onboarding/persona-template.md`) — the pattern this persona is built
from (Liquid Death's "Business Applications Manager") is the same shape of
company as True Classic: a DTC-first consumer brand where an operations/
supply-chain/business-systems function, not a large dedicated IT department,
most likely owns retail-partner integration work. **Named contact:
unconfirmed.** No specific person identified — would need an actual
enrichment step (e.g. a LinkedIn search for "Operations," "Supply Chain," or
"Business Systems" titles at True Classic) that hasn't been run. Not guessed
at.

**Secondary — executive sponsor.** At 162 employees against ~$500M revenue,
True Classic is lean enough that a co-founder is plausibly still close to a
decision like this, and there's a real, named, public option here: **Ben
Yahalom, CEO**, who is the same person quoted in press specifically about the
Target partnership's growth potential (per Company basics/Signal sourcing
above) — not a guess at who the executive is, an already-public fact. He's
the natural economic-buyer-side thread per the persona template's pairing
logic, since the ops lead is the likely champion but probably isn't the one
who'd approve new vendor spend at this size of company.

## Prior relationship check

**No relationship found.** True Classic does not appear among Orderful's
public customer logos or case studies (`../onboarding/company-understanding-inventory.md`'s
"Current customers" section) — new, as far as public information
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

## Resulting outreach sequence

Score = Hot, so per
[`../templates/outreach-sequence.md`](../templates/outreach-sequence.md) this
gets the 5-step, ~2-week Hot cadence, **run as two parallel threads, not one**
— per that file's multi-threading section and the Persona mapping above.
Thread A (the primary, unconfirmed ops contact) runs the full 5 steps
starting Day 0; Thread B (Ben Yahalom, CEO) runs a shorter 3-touch version
starting Day 2, offset rather than synchronized so it reads as two people
independently reaching out, not one coordinated blast. Per `business.yaml`'s
`outbound_send: draft_only`, every step in both threads is prepared in
advance as drafts; a human still decides whether and when each one
actually goes, and whether to keep going if an earlier step gets a reply.

### Thread A — primary (unconfirmed ops/systems contact)

Full 5-step cadence, starting Day 0 — the hands-on champion pitch: speed and
not needing to add headcount to handle it.

### Step 1 — Day 0, Email

This is **Template 1** from
[`../templates/outreach-templates.md`](../templates/outreach-templates.md)
(consumer brand ops lead × new retailer launch) with its variables filled in
from the confirmed facts above — not a bespoke message written just for this
account.

| Variable | Value used | Source |
|---|---|---|
| `{{contact_first_name}}` | *unconfirmed — see Persona mapping* | n/a |
| `{{company_name}}` | True Classic | Company basics |
| `{{retailer_name}}` | Target | Signal |
| `{{signal_detail}}` | the 460-store Target rollout, after first testing on Target.com in October | Signal / Recent activity |
| `{{proof_point}}` | Liquid Death — 80% reduction in time to set up trading partners, "own the keys to the kingdom... not rely on outside parties" | `../onboarding/proof-points.md` |
| `{{sender_name}}` | *n/a — set at send time* | n/a |

> **Subject:** Congrats on the Target launch — a question on scaling it
>
> Hi [Name] — saw the 460-store Target rollout, after first testing on
> Target.com back in October — congrats, that's a real step up.
>
> Curious how EDI is holding up as Target scales alongside whatever other
> wholesale partners True Classic runs today. Liquid Death saw an 80%
> reduction in time to set up trading partners after switching to Orderful
> — happy to walk through what that could look like for you here.
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

### Step 2 — Day 3, LinkedIn

Connection request + short note. Uses a different proof point than step 1
(the network-size stat, not the case-study names) so the second touch doesn't
just repeat the first one on a new channel.

> Hi [Name] — sent a note on the Target launch a few days ago, figured I'd
> connect here too. One more data point in case it's useful: Orderful's
> network already covers 10,000+ trading partners, so a lot of new
> connections end up being "join what's already there" rather than building
> from scratch. Would love to hear how the rollout's going.

### Step 3 — Day 6, Email — angle switch to compliance risk

Per the brief's client-specific priorities, whether Target's Perfect Order
Program (signal #2) applies to True Classic's account is
**unconfirmed** — so this step asks, per `outreach-templates.md`'s rule,
rather than asserting it as fact the way Template 2 would for a confirmed
case.

> **Subject:** Quick compliance question on the Target side
>
> Hi [Name] — following up with a different angle: Target's rolled out
> stricter automated compliance checks recently (ASN accuracy, barcode
> scanning) that apply per-carton, not just at onboarding. Not sure if
> that's already live on your account or not, but if it is, it's worth
> knowing before it shows up as a deduction rather than after.
>
> Happy to help you check either way — no pitch attached to that specifically.
>
> [Sender name]

### Step 4 — Day 10, Phone + follow-up email

**Voicemail (if no answer):** mirrors the original hook, adds one proof point
verbally, flags the email that's about to follow.

> "Hi [Name], this is [Sender name] from Orderful — following up on a couple
> notes about your Target launch. Brands like Liquid Death have used us to
> cut the time it takes to stand up a new trading partner by 80%. I'll send
> a quick email right after this with their case study — would love 15
> minutes if the timing's right."

**Follow-up email**, sent right after the call attempt:

> **Subject:** Tried you by phone — here's what I meant
>
> Hi [Name] — just called and missed you. Wanted to share Liquid Death's
> story specifically, since it's a similar shape to what True Classic's
> doing right now — a DTC brand scaling into wider retail distribution and
> using Orderful to keep EDI from being the bottleneck.
>
> [link to Liquid Death case study](https://www.orderful.com/resources/case-studies/liquid-death)
>
> Open to 15 minutes whenever works.
>
> [Sender name]

### Step 5 — Day 14, Email — breakup

Low-pressure exit, per the sequence template's design — closes the loop
rather than trailing off unanswered.

> **Subject:** Will stop here
>
> Hi [Name] — haven't been able to connect, so I'll stop following up for
> now. If EDI becomes a real pain point as the Target rollout scales (or if
> the compliance question from a few emails back turns out to matter), feel
> free to reach out directly — happy to help whenever it's useful.
>
> [Sender name]

### Thread B — secondary (Ben Yahalom, CEO), starting Day 2

Shorter, executive-appropriate cadence per `outreach-sequence.md`'s
multi-threading note — 3 touches, not 5, and a different angle from Thread A:
Thread A is the hands-on champion pitch (speed, no headcount needed); Thread
B is the growth-protection angle, since Yahalom is the one on record framing
the Target relationship as something to grow, not just launch.

**Step B1 — Day 2, Email**

> **Subject:** Congrats on Target — one thing worth protecting as it scales
>
> Hi Ben — congrats on the Target rollout, and on the read that there's room
> to grow it further. The EDI layer under a partnership like that is usually
> invisible right up until it isn't — a missed ASN or a barcode issue becomes
> a chargeback and a strained relationship exactly while you're trying to
> prove the channel out.
>
> We work with brands in True Classic's position — Liquid Death cut their
> time to stand up a new trading partner by 80% after switching — to keep
> that layer from being the thing that caps how fast a retail partnership
> can grow. Worth a short call as you're scaling this?
>
> [Sender name]

**Step B2 — Day 9, LinkedIn**

> Hi Ben — following up briefly on the note about Target. No pressure to
> reply if this isn't the right level for you to be looking at day-to-day —
> happy to connect with whoever owns EDI operationally if that's a better
> fit.

**Step B3 — Day 16, Email — breakup**

> **Subject:** Will leave this with you
>
> Hi Ben — haven't heard back, so I'll stop here. If EDI ever becomes
> something slowing down the Target relationship (or the next one), feel
> free to loop in whoever's closest to it on your team — happy to help
> either way.
>
> [Sender name]

Thread B's second touch explicitly offers to redirect to the real operational
contact — a deliberate hedge, since Thread A's contact is unconfirmed and
Yahalom, as CEO of a $500M-revenue company, is very plausibly not the person
who should own this conversation day to day.

### What this sequence deliberately leaves unresolved

`[Name]` and `[Sender name]` stay unfilled throughout Thread A — no
enrichment step has run to find a real contact at True Classic.
Step 3's compliance angle stays a question, not a claim, because that fact is
unconfirmed per the brief above. Thread B uses Ben Yahalom's real,
public name and title (he's on record about this exact partnership) but
everything about whether he's the right person to reach, and how
he'd react, is unconfirmed — that's exactly why Thread B's own second touch
offers to redirect rather than assuming he's staying on the thread. None of
this has been sent; True Classic has not been contacted.
