# CLAUDE.md

Auto-loaded at the start of every session in this repo (or any client instance
forked from it) — Claude Code reads a file with this exact name automatically,
no one has to remember to point at it.

## In the template itself (this repo)

Read `docs/OFFERING_SPEC.md` first, then `docs/DECISIONS.md`. `README.md`'s
"Start here" section has the fuller map.

## In a client instance

This file plays a different role depending on where that instance actually is:

**Before onboarding is confirmed** (still draft, gaps open) — this file is just
a router. Read `onboarding/` directly; each file shows its own evidence and
open gaps. Don't treat anything as settled just because it's written down —
check each file's own gap notes first.

**Once onboarding is confirmed** (every open question actually resolved with
the client) — this file becomes the operating brief: the current, consolidated
ICP, personas, signal tiers, and governance posture, compiled from the
onboarding files. Meant to be read once per session by whatever's actually
doing the work (research, drafting), instead of re-deriving context from six
separate files every time.

Compile it at that point, not before — a brief built from draft content just
launders unconfirmed guesses as settled fact, which is exactly what
`onboarding/`'s gap-tracking exists to prevent.

## Status in a given instance

State plainly here whether this file is currently a router (onboarding still in
progress) or a compiled brief (onboarding confirmed) — so anyone or anything
reading it knows which mode it's in before trusting what follows.

## Status: router.

This is not a live client engagement. It's a demonstration instance built for
[Orderful](https://www.orderful.com/) to show their CRO (Mike Head) what this
offering looks like applied to a real company, before any engagement exists.

`onboarding/company-understanding-inventory.md`, `icp-template.md`,
`persona-template.md`, and `signal-inventory-template.md` are filled in from
public research only (orderful.com, their own case studies and blog, retailer
EDI-compliance research, competitor reviews, retail trade press) — no access
to Orderful's actual customers, CRM, inbound funnel, or sales team. Every
finding across all four is a hypothesis to validate with Orderful directly,
not settled fact — each file's own "Open gaps" / "Client-verified signals"
section says exactly what's still missing. `tech-stack-audit-template.md` and
`storage-decision-worksheet.md` are still blank on purpose — they depend on
Orderful's actual tools and data access, which public research can't
substitute for at all (unlike ICP/persona/signals, which can at least start
from public evidence).

The concept continues past onboarding into `score/scoring-model.md` (fit ×
signal → tier), `score/eval-example.md` (how those guesses get corrected over
time), `templates/account-research-brief.md`, `templates/outreach-templates.md`,
and `templates/outreach-sequence.md` (draft messages, paced and threaded to
two contacts). `output/example-brief-true-classic.md` runs one real company
through that entire chain. `HOW_THIS_WORKS.md` is the plain-language summary
of all of it, written for a reader who won't open the other files —
read that first if you're orienting to this repo for the first time.

**Do not compile this into an operating brief.** There's no real engagement to
compile from yet.
