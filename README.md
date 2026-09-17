# gtm-bd-operator-orderful

A **demonstration instance** of [gtm-bd-operator](https://github.com/jwcollins6/gtm-bd-operator)
— John Collins's front-end business development offering — built to show
[Orderful](https://www.orderful.com/) (modern EDI platform) what this looks
like applied to their actual business.

**This is not a live client engagement.** Orderful has no contract with John
and hasn't confirmed anything in here. It was built to show their CRO, Mike
Head, a concrete example ahead of a conversation. Treat every finding as a
hypothesis pulled from public research, not a verified fact about Orderful's
business — every file that makes a claim also says where it came from and
what's still unconfirmed.

## Start here

**[`HOW_THIS_WORKS.md`](HOW_THIS_WORKS.md) — read this first.** Plain-
language explanation of what this does, an AI-vs-human breakdown of who's
responsible for what, what using it day to day would look like for someone
on your team, and what it would actually need from Orderful to go from demo
to real. Doesn't require reading anything else in this repo first.

Everything below is what that explainer is summarizing — useful if you want
to go deeper on a specific piece.

## What's in here

**Onboarding — who Orderful should target, and why** (`onboarding/`)
- [`company-understanding-inventory.md`](onboarding/company-understanding-inventory.md) — what Orderful sells, positioning, differentiation, company facts
- [`icp-template.md`](onboarding/icp-template.md) — which companies fit, and why
- [`persona-template.md`](onboarding/persona-template.md) — who at those companies, paired with a second contact for multi-threading
- [`signal-inventory-template.md`](onboarding/signal-inventory-template.md) — what "reach out now" actually looks like, tiered by urgency
- `tech-stack-audit-template.md`, `storage-decision-worksheet.md` — intentionally blank; see "What this needs from Orderful" in `HOW_THIS_WORKS.md`

**Turning that into action** (`score/`, `templates/`)
- [`score/scoring-model.md`](score/scoring-model.md) — fit × signal urgency → a Hot/Warm/Nurture/Disqualify tier and a routing action
- [`score/eval-example.md`](score/eval-example.md) — how the guesses in this repo would actually get corrected over time, with an illustrative example
- [`templates/account-research-brief.md`](templates/account-research-brief.md) — the research shape every surfaced account gets
- [`templates/outreach-templates.md`](templates/outreach-templates.md) — reusable draft messages by persona × signal
- [`templates/outreach-sequence.md`](templates/outreach-sequence.md) — how those drafts get paced across channels and threaded to two contacts, not one

**One real company run through the whole chain**
- [`output/example-brief-true-classic.md`](output/example-brief-true-classic.md) — True Classic (not an Orderful customer, just launched at 460 Target stores): signal → fit check → both contacts mapped → scored Hot → both outreach threads written out day by day

**Config**
- [`business.yaml`](business.yaml) — what's publicly knowable about Orderful filled in; everything needing an actual conversation left `TBD`
- [`CLAUDE.md`](CLAUDE.md) — auto-loaded by Claude Code at the start of every session; router mode, since there's no confirmed engagement to compile into an operating brief

## Status

Pre-engagement demo, private repo, built 2026-09-17. Everything listed above
under Onboarding and Turning that into action is filled in as a
research-derived concept, not client-verified — each file says so plainly at
the top and lists its own open gaps. See the parent template's
[`README.md`](https://github.com/jwcollins6/gtm-bd-operator/blob/main/README.md)
for what the full offering and onboarding process look like once an
engagement is real.
