# Scoring model concept — Orderful

**Status: research-derived concept, not client-verified.** Built 2026-09-17.
Per `../docs/OFFERING_SPEC.md` and `../docs/process/outbound-pipeline.md`
stage 5 ("Score fit x intent") and stage 8 ("Route by score"), this is what
that scoring step could look like for Orderful specifically — combining
`../onboarding/icp-template.md` (fit) with `../onboarding/signal-inventory-template.md`
(intent/urgency) into a single tier that decides what happens next.

This is normally `score/` code, built per client once the data platform track
is decided (see this file's neighbors — `score/README.md`'s own note). Since
there's no real engagement or platform decision yet, this stays a rubric/
concept doc, not implementation — the weights and thresholds below are
illustrative, not tuned to any real outcome data. See "Open gaps."

## The two inputs

**Fit score** — does this company match `icp-template.md` at all, independent
of timing:

| Fit dimension | 0 points | 1 point | 2 points |
|---|---|---|---|
| Industry/company type | Neither ICP shape (consumer brand entering retail, or logistics/carrier/3PL) | Adjacent (e.g. manufacturer, SaaS platform) | Direct match to one of the two primary shapes |
| Size / trading-partner band | Too small to ever need >1-2 partners, no growth trajectory | Unclear/unconfirmed | Scaling trading-partner count now or clearly about to |
| Geography | Outside North America, EDIFACT-only need | International but plausible | North America (X12) |

**Any disqualifier from `icp-template.md` present** (locked into a
happy incumbent with no visible pain, no wholesale/retail ambition, needs
outside Orderful's supported scope) — **kill switch**: score goes to
`Disqualify` regardless of the table above. Fit points otherwise sum to a
max of 6.

**Intent score** — from `signal-inventory-template.md`'s tiers, whichever
signal(s) actually fired on this account:

- Tier 1 signal fired (new retailer launch, compliance-policy change, EDI job
  posting, matching complaint pattern) → **3 points**
- Tier 2 signal fired (ERP migration, new DC/3PL/geo expansion) → **2 points**
- Tier 3 signal fired (funding/M&A) → **1 point**
- **Signal stacking**: if more than one signal fires on the same account,
  take the highest tier's points and add **+1** per additional distinct
  signal (capped at +2) — a company that both just launched at a retailer
  *and* is hiring an EDI analyst is a stronger case than either alone.

## Combined tier

| | Intent: Low (1) | Intent: Med (2-3) | Intent: High (4+) |
|---|---|---|---|
| **Fit: High (5-6)** | Nurture | Warm | **Hot** |
| **Fit: Med (3-4)** | Nurture | Warm | Warm (fast-track) |
| **Fit: Low (0-2)** | Disqualify | Nurture | Nurture |
| **Disqualifier present** | Disqualify, regardless of the above | | |

"Warm (fast-track)" is called out separately: fit isn't a perfect match, but
a Tier 1 signal firing (a hard, dated event like a retailer launch) can still
justify a look, since EDI compliance is a real gate regardless of how well a
company otherwise resembles the ICP. That distinction from plain "Warm"
should get pressure-tested against real outcomes before being trusted.

## Routing per tier (outbound-pipeline.md stage 8)

- **Hot** — generate the account research brief and a draft outreach the same
  day; notify the assigned rep for same-day human review and send (this
  instance's `business.yaml` has `outbound_send: draft_only` — a human always
  sends, this doesn't change that, it just changes speed of getting in front
  of one).
- **Warm / Warm (fast-track)** — generate the brief and draft, queue into the
  next outreach batch (cadence TBD — see `business.yaml`'s `TBD` eval
  cadence) rather than same-day.
- **Nurture** — log the account and signal; no brief or draft yet. Re-evaluate
  automatically if a second, stronger signal fires later (this is what makes
  signal stacking matter operationally, not just as a scoring bonus).
- **Disqualify** — log the specific disqualifier that fired; suppress from
  future signal-triggered alerts for a cooldown period (90 days, arbitrary
  placeholder) unless a materially different signal type fires.

## Worked example

See [`../output/example-brief-true-classic.md`](../output/example-brief-true-classic.md)
for this scoring model applied end-to-end to a real company (True Classic) —
Fit and Intent both scored out, landing on **Hot**, with the resulting draft
outreach shown.

## Open gaps

- **Every weight and threshold here is a guess**, not derived from any real
  won/lost deal data — there isn't any yet. This needs the eval loop
  (`../docs/eval/eval-loop.md`) running against real outcomes before any of it
  should actually gate what a rep sees or when.
- Whether "Warm (fast-track)" is a real, useful distinction or just adds
  confusion — untested.
- The 90-day disqualify cooldown is arbitrary, not derived from Orderful's
  actual sales cycle length.
- No client-side confirmation that fit dimensions should be weighted equally
  (industry match, size, geography each worth up to 2 points) — Orderful's
  own team may weight one of these far more than the others in practice.
