# External reference patterns

Specific techniques worth borrowing from things seen out in the world — parked
here for when there's an actual build decision they're relevant to, never
treated as a lineage this repo forks from or has to reconcile with. See
`../OFFERING_SPEC.md` and `../DECISIONS.md` for what's actually decided; nothing
in this file changes any of that on its own.

## Source: Troy (@troyaitken_) on X, "How to Build an Outbound Engine That Gets Smarter Every Week Without Anyone Touching It" (2026-09-15)

Context: a cold-email agency's outbound-only engine for one client, running
30k-100k emails/day. Single-client, single-hypothesis, high-volume,
fully-automated-scoring — a different shape of problem than this repo's
two-directional, multi-client, per-client-onboarded, draft-only-starting-point
model. Relevant only once actually building the outbound copy/scoring code
(`../../skills/`, `../../output/`, `../../score/`) for a real client instance.

- **Controlled-vocabulary "angle" taxonomy.** Every messaging angle gets a
  stable key (e.g. `fica_math`, `skeptic_disarm`) whose description can evolve
  but whose key never changes once assigned. Scoring is built on the key, not
  free-form descriptions — this is what lets performance data accumulate across
  campaigns instead of resetting every time the same idea gets phrased slightly
  differently. This repo currently has no equivalent concept for outbound copy
  variants — worth adopting when `skills/`/`output/` get built for a real
  client.
- **Automated promotion/retirement thresholds.** A concrete, numeric template
  for the autonomy-graduation criteria this repo deliberately deferred (see
  `../eval/eval-loop.md`). Their rule, for reference (not to copy verbatim —
  calibrate to actual volume): a campaign is "validated" at ≥1 meeting booked,
  or ≥1,000 delivered with ≥1 positive reply; "retired" at ≥1,000 delivered
  with zero positive replies, unless reply-tagging itself looks broken (checked
  separately, so a tracking failure doesn't get misread as a copy failure). A
  messaging angle gets promoted into a reusable library only once validated
  across 2+ separate campaigns with minimum volume and reply counts.
- **Voice-of-customer mining from public communities.** Pulling actual sourced,
  quoted phrases (not paraphrased summaries) that real people in the buyer's
  role use — Reddit threads, G2 reviews, LinkedIn comments. More specific than
  this repo's current `../../onboarding/company-understanding-inventory.md`
  approach (client's own customers/messaging/website) — worth adding as a
  technique inside that inventory, not a replacement for it.
- **Concrete governance rules baked into code.** A banned-phrase list plus a
  "proximity rule" (say "can help," never claim the outcome as already
  happening). A real example of what `../../governance/README.md` is currently
  just a placeholder for.
- **List-recycle discipline.** A 90-day cooldown before re-contacting someone,
  capped at 3 total resends, plus dedup/DNC suppression on every contact
  selection. This repo hasn't addressed contact recycling/resend cadence at all
  yet — worth folding into a future version of
  `../process/outbound-pipeline.md`.
- **Weekly cadence, concretely instantiated.** A Friday read-only scorecard
  (named repliers, which angle/variant triggered each reply, the actual reply
  text) followed by a Monday action pass. Validates this repo's "spot-check
  weekly or ad hoc" decision (`../eval/eval-loop.md`) as a reasonable pattern,
  and is a decent template for what that weekly review could concretely look
  like once there's real client data.
- **Not applicable, don't adopt:** the fully-autonomous "no human touches a
  send" posture only works for blind high-volume cold email with no individual
  relationship at stake per contact — not evidence that this repo's draft-only
  starting point is behind, just a different risk calculus. Same with their
  specific single-Railway-dispatcher architecture — one example, not a
  prescription, since architecture stays a per-client "how" decision here.
