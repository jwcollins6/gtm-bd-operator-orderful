# workflows/

Orchestration for this client instance: what triggers what, in what order (signal
detected -> score -> draft; inbound event -> identity check -> qualify -> route).
Empty in the template — the actual trigger/orchestration tooling (n8n or otherwise)
is a "how" decision made per client, not specified generically here.

## What would go here for Orderful

For outbound, the trigger chain is already fully specified conceptually —
this file would hold whatever actually implements it as a running trigger:
`../skills/signal-detection-skill.md` fires → `../skills/account-research-skill.md`
runs (with its own early-exit on a failed ICP check) →
`../score/scoring-model.md`'s tier decides routing → for Warm/Hot,
`../templates/outreach-templates.md` and `outreach-sequence.md` produce the
draft. Inbound has no equivalent work done for Orderful at all yet — every
onboarding file built in this repo (`../onboarding/`) focused entirely on
outbound, so there's no inbound trigger chain to even describe here yet,
let alone implement.
