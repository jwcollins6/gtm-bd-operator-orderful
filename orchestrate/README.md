# orchestrate/

Empty in the template. Built per client once onboarding (../onboarding/) has
determined the data platform track (A: live-connected, no custom code needed here
beyond calling the client's real tools; B: build against the system of record
chosen in storage-decision-worksheet.md) and the tech-stack audit findings. See
../docs/OFFERING_SPEC.md for why this stays a "how" decision made per client
rather than something generic here.

## What would go here for Orderful

The glue that wires `../ingest/` → `../enrich/` → `../score/scoring-model.md`'s
logic (as real code, not just the concept doc) → drafting into one running
pipeline on a schedule set by the team (per `../GOING_LIVE.md` item 4) —
likely a tool like n8n handling the triggers, with Claude still called for
the judgment-heavy step (writing the actual draft) rather than replaced by
it. For Warm/Hot accounts specifically, per
`../skills/signal-detection-skill.md`'s chain, this is what would actually
run that chain unattended instead of a rep or Claude Code session kicking it
off. Not built because there's no `../ingest/` or `../enrich/` code yet for
this to wire together.
