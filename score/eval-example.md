# How this gets smarter — eval loop applied to Orderful

**Status: illustrative concept, not real data.** Built 2026-09-17. This
operationalizes `../docs/eval/eval-loop.md` (the general, decided mechanism —
read that first) and `../docs/process/outbound-pipeline.md` stage 11
specifically for what's been built in this repo: the scoring model, the
signal inventory, the persona/thread pairings, and the outreach
templates/sequence. **Every number and outcome below is a made-up
illustration of the mechanism, not a real campaign result** — nothing in
this repo has been sent to anyone.

## The concept, plainly

Nothing in `score/scoring-model.md`, `onboarding/signal-inventory-template.md`,
or `templates/outreach-templates.md` was derived from a real outcome —
every weight, tier, and proof-point choice is a reasoned guess. The eval
loop is how those guesses get replaced with real ones, without ever letting
the system quietly adjust itself:

1. **A human manually marks outcomes** — per account run through the
   pipeline, someone (John, or eventually someone at Orderful) marks: did
   this account reply, did a meeting get booked, and separately —
   regardless of reply — was this a good account to have surfaced
   at all (the two different questions `eval-loop.md` calls out for
   outbound).
2. **Findings get surfaced, not auto-applied.** The review produces a set of
   "here's what the data suggests" notes for a human to act on. Nothing in
   `score/scoring-model.md`'s weights or `signal-inventory-template.md`'s
   tiers changes by itself.
3. **A human decides what to change** — bump a signal's tier,
   adjust a fit weight, swap a proof point, cut a thread that isn't working
   — and edits those files directly, the same way any of this repo's
   concept docs get revised.
4. **No fixed cadence** — spot-check whenever there's enough volume to say
   something real, not on a forced weekly schedule (per `eval-loop.md`).

This is the same posture as `business.yaml`'s `outbound_send: draft_only` —
a deliberate, conservative starting point (human-reviewed, not
self-adjusting), expected to evolve later, not skipped to now.

## Illustrative worked example

Imagine a spot-check after running roughly 20 Hot-tier accounts through the
multi-threaded sequence (`templates/outreach-sequence.md`) over some
hypothetical stretch of time. A reviewer marks each one and looks for
patterns:

| Signal that fired | Accounts run | Meetings booked | Reviewer's note |
|---|---|---|---|
| #1 New retailer launch | 8 | 3 | Strong — real, dated urgency seems to convert |
| #2 Compliance-policy change | 5 | 0 | 2 of the 5 turned out **not to be confirmed suppliers of that retailer** — the signal fired on an unverified assumption, not a real trigger |
| #4 Displacement complaints | 4 | 1 | Replies came in, but tone read as "just gathering info," not urgent — proof point may be underselling the cost of staying put |
| #3 EDI job posting | 3 | 1 | Too small a sample to say much yet |

And on threading specifically: **Thread B (the executive/economic-buyer
thread) got zero replies across all 20 accounts**, while Thread A (the
primary/champion contact) accounted for all 5 meetings.

## What a human would do with this

Per the eval loop's own rule, none of this changes anything automatically —
here's what a reviewer would take back to the actual files:

- **Signal #1 keeps its Tier 1 status, and this is exactly the kind of
  result that would justify eventually weighting it even more heavily** in
  `score/scoring-model.md`'s intent scoring, once there's enough volume to
  be confident it's not noise.
- **Signal #2's problem isn't the signal, it's the verification step** — 2
  of 5 false-fires on an unconfirmed supplier relationship is exactly the
  operational cost flagged in `signal-inventory-template.md`'s Open Gaps.
  The fix isn't dropping the signal, it's tightening the check (e.g.
  requiring two independent confirming sources before treating it as fired,
  not one) before it reaches Hot.
- **Template 3's proof point (NFI's 5-day onboarding stat) may need
  replacing** for the displacement persona — worth testing a sharper
  cost-of-inaction framing instead of a pure speed stat, and editing
  `templates/outreach-templates.md` directly once there's a better option.
- **Thread B is the one worth questioning most directly.** Zero replies
  across 20 accounts, in this illustration, would be a real signal that
  either the touch count/timing is off, the angle is wrong, or executive
  threading isn't worth the effort for this persona at all — not something
  to keep running unexamined just because `onboarding/persona-template.md`
  theorized it should work. This is precisely why that file's own Open Gaps
  section already flags the pairing as reasoned, not proven.

## What stays exactly as decided in `../docs/eval/eval-loop.md`

- Feedback stays manual — no automatic pull from a CRM or calendar, and
  nothing above should be read as the system adjusting itself.
- Autonomy (`business.yaml`'s `outbound_send: draft_only`) doesn't move
  based on this kind of review alone — that's a separate, deliberately
  conservative decision on its own crawl/walk/run timeline.
- No fixed review cadence — this kind of look happens when there's enough
  real volume to say something, not on a forced schedule.

## Open gaps

- What counts as "enough volume to trust a pattern" (is 20 accounts
  enough to act on a 0% Thread B reply rate, or just noise?) is unconfirmed
  and would need real judgment once real numbers exist.
- Whether Orderful's own team would even want John doing this marking, or
  would want to do it themselves inside their own CRM, is an open
  operating-model question, not a technical one — the mechanism doesn't
  depend on which of them physically does it.
