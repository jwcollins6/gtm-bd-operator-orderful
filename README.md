# gtm-bd-operator-orderful

A **demonstration instance** of [gtm-bd-operator](https://github.com/jwcollins6/gtm-bd-operator)
— John Collins's front-end business development offering — built to show
[Orderful](https://www.orderful.com/) (modern EDI platform) what this looks
like applied to their actual business.

**This is not a live client engagement.** Orderful has no contract with John
and hasn't confirmed anything in here. It was built to show their CRO, Mike
Head, a concrete example ahead of a conversation, not to represent a completed
onboarding. Treat every finding in `onboarding/` as a hypothesis pulled from
public research, not a verified fact about Orderful's business.

## Start here

- [`CLAUDE.md`](CLAUDE.md) — auto-loaded by Claude Code at the start of every
  session. Router mode — there's no confirmed engagement to compile into an
  operating brief.
- [`onboarding/company-understanding-inventory.md`](onboarding/company-understanding-inventory.md),
  [`icp-template.md`](onboarding/icp-template.md),
  [`persona-template.md`](onboarding/persona-template.md), and
  [`signal-inventory-template.md`](onboarding/signal-inventory-template.md) —
  the four onboarding files that are filled in, built from Orderful's own
  public site, blog, and case studies plus independent research into EDI
  buying triggers (retailer compliance requirements, competitor reviews,
  retail trade press) as of 2026-09-17. No access to their actual customer
  list, CRM, inbound funnel, or sales team — those sections are marked as open
  gaps in each file, not guessed at.
- [`business.yaml`](business.yaml) — what's publicly knowable about Orderful
  filled in; everything that depends on an actual conversation (track, storage,
  autonomy posture) left `TBD`.
- [`score/scoring-model.md`](score/scoring-model.md) and
  [`templates/outreach-templates.md`](templates/outreach-templates.md) — a
  concept for how fit × intent scoring and draft outreach would actually work
  downstream of the onboarding files, plus
  [`output/example-brief-true-classic.md`](output/example-brief-true-classic.md),
  one real, worked example threading a signal through a research brief, a
  score, and a filled-in draft, end to end.

## Why this exists

To make the offering concrete for a specific prospect rather than pitching it
in the abstract — showing Orderful's CRO what a real onboarding pass and
instance for their own company would start to look like, using only what's
already public about them.

## Status (2026-09-17)

Pre-engagement demo. `onboarding/company-understanding-inventory.md`,
`icp-template.md`, `persona-template.md`, and `signal-inventory-template.md`
are filled in as research-derived concepts — notably, the signal inventory's
top signal (a brand launching at a major retailer) is directly validated
against a real, named Orderful customer (Caraway's 2026 Walmart launch), not
just theorized. The concept now runs one full step further downstream:
`score/scoring-model.md` turns ICP fit + signal tier into a Hot/Warm/Nurture
tier and a routing action, `templates/outreach-templates.md` turns persona +
signal into a reusable draft-message template, and
`output/example-brief-true-classic.md` runs a real company (True Classic,
not an Orderful customer, freshly launched at 460 Target stores) through the
whole chain — signal, fit check, persona mapping, score, and a filled-in
draft — as one worked example. `tech-stack-audit-template.md` and
`storage-decision-worksheet.md` are still blank on purpose — skipped for now,
since they depend on Orderful's actual tools/data access in a way public
research can't substitute for at all. See the parent template's
[`README.md`](https://github.com/jwcollins6/gtm-bd-operator/blob/main/README.md)
for what the full offering and onboarding process look like once an engagement
is real.
