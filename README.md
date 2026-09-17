# gtm-bd-operator-orderful

An AI GTM example, built to show Mike Head (Orderful's CRO) what I've
built — [gtm-bd-operator](https://github.com/jwcollins6/gtm-bd-operator), a
front-end business development operator, applied to
[Orderful](https://www.orderful.com/) (modern EDI platform).

## Start here

**[`HOW_THIS_WORKS.md`](HOW_THIS_WORKS.md) — read this first.** Plain-
language explanation of what this does, an AI-vs-human breakdown of who's
responsible for what, what using it day to day would look like for someone
on your team, and what it would need from Orderful to go from demo
to real. Doesn't require reading anything else in this repo first.

**[`GOING_LIVE.md`](GOING_LIVE.md) — read this second.** The mechanical
follow-up: actual setup steps, split into what ops does once versus what
each rep does individually, and a rep's day-to-day workflow once it's
running.

Everything below is what those two explainers are summarizing — useful if
you want to go deeper on a specific piece.

## What's in here

**Onboarding — who Orderful should target, and why** (`onboarding/`)
- [`company-understanding-inventory.md`](onboarding/company-understanding-inventory.md) — what Orderful sells, positioning, differentiation, company facts
- [`icp-template.md`](onboarding/icp-template.md) — which companies fit, and why
- [`persona-template.md`](onboarding/persona-template.md) — who at those companies, paired with a second contact for multi-threading
- [`signal-inventory-template.md`](onboarding/signal-inventory-template.md) — what "reach out now" looks like, tiered by urgency
- [`proof-points.md`](onboarding/proof-points.md) — real Orderful case-study quotes and stats, one library every outreach template draws from
- `tech-stack-audit-template.md`, `storage-decision-worksheet.md` — intentionally blank; see "What this needs from Orderful" in `HOW_THIS_WORKS.md`

**Turning that into action** (`skills/`, `score/`, `templates/`)
- [`skills/signal-detection-skill.md`](skills/signal-detection-skill.md) — how each of the 7 signals actually gets found, and how a hit chains straight through to a finished brief, score, and draft
- [`skills/account-research-skill.md`](skills/account-research-skill.md) — the research process a detected signal chains into
- [`score/scoring-model.md`](score/scoring-model.md) — fit × signal urgency → a Hot/Warm/Nurture/Disqualify tier and a routing action
- [`score/eval-example.md`](score/eval-example.md) — how the guesses in this repo would get corrected over time, with an illustrative example
- [`templates/account-research-brief.md`](templates/account-research-brief.md) — the research shape every surfaced account gets
- [`templates/outreach-templates.md`](templates/outreach-templates.md) — reusable draft messages by persona × signal
- [`templates/outreach-sequence.md`](templates/outreach-sequence.md) — how those drafts get paced across channels and threaded to two contacts, not one

**One real company run through the whole chain**
- [`output/example-brief-true-classic.md`](output/example-brief-true-classic.md) — True Classic (not an Orderful customer, just launched at 460 Target stores): signal → fit check → both contacts mapped → scored Hot → both outreach threads written out day by day

**Config**
- [`business.yaml`](business.yaml) — what's publicly knowable about Orderful filled in; everything needing an actual conversation left `TBD`
- [`CLAUDE.md`](CLAUDE.md) — auto-loaded by Claude Code at the start of every session; router mode, since there's no confirmed engagement to compile into an operating brief

**Not built, but previewed** (`ingest/`, `enrich/`, `orchestrate/`, `tests/`, `workflows/`, `governance/`)
No real code or client-specific policy exists in any of these yet — each
one's own `README.md` now says concretely what would go there for Orderful
specifically (e.g. `ingest/`'s would be the code version of the signal-
detection skill's search process), not just "empty, built later."

## Status

Demo built 2026-09-17. Everything listed above
under Onboarding and Turning that into action is filled in as a
research-derived concept, not client-verified — each file says so plainly at
the top and lists its own open gaps. See the parent template's
[`README.md`](https://github.com/jwcollins6/gtm-bd-operator/blob/main/README.md)
for what the full offering and onboarding process look like when it's built
for a real client.
