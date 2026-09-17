# Outreach templates by persona × signal — Orderful

**Status: research-derived concept, not client-verified.** Built 2026-09-17.
This is the reusable asset outbound stage 9 (`../docs/process/outbound-pipeline.md`)
actually draws from — not one-off examples written per company, but a small
library of templates keyed by **which persona** (`../onboarding/persona-template.md`)
and **which signal** (`../onboarding/signal-inventory-template.md`) fired, with
variables filled in per account from that account's research brief
(`account-research-brief.md`). One worked instance of the first template
below, filled in for a real company, is at
[`../output/example-brief-true-classic.md`](../output/example-brief-true-classic.md).

**Every `{{variable}}` must come from a confirmed fact in that account's
research brief, never invented to make a template read more specifically** —
per `../governance/README.md`. If a variable isn't confirmed, the template
should ask a question instead of asserting a fact (see the True Classic
example: it asks about their current EDI setup rather than guessing at it).

Per `business.yaml`'s `outbound_send: draft_only`, every output of these
templates is a draft for human review, never sent automatically.

## Variables used across templates

- `{{contact_first_name}}` — from persona-mapped enrichment; if unconfirmed,
  the draft should say so rather than use a placeholder greeting as if it
  were real.
- `{{company_name}}`
- `{{retailer_name}}` — the retailer tied to the signal (Target, Walmart,
  Kroger, etc.)
- `{{signal_detail}}` — the specific, sourced fact that fired the signal
  (e.g. "460 Target stores," "the new $0.75/carton ASN accuracy fine")
- `{{proof_point}}` — a real Orderful case-study quote/stat, chosen to match
  the persona (see each template below for which one fits)
- `{{sender_name}}`

## Template 1 — Consumer brand ops lead × new retailer launch (signal #1)

**When to use:** persona = "Ops/Systems lead at a consumer brand entering
retail"; signal = Tier 1 new major-retailer launch.
**Proof point to use:** Liquid Death's case study ("own the keys to the
kingdom," 80% reduction in time to set up trading partners) — matches this
persona's stated priority of not depending on an outside party they can't see
into.

> **Subject:** Congrats on the {{retailer_name}} launch — a question on
> scaling it
>
> Hi {{contact_first_name}} — saw {{signal_detail}} — congrats, that's a real
> step up.
>
> Curious how EDI is holding up as {{retailer_name}} scales alongside
> whatever other retail partners {{company_name}} runs today. We work with
> brands in a similar spot ({{proof_point}}) who've used Orderful to connect
> once and onboard new retail partners in days instead of months, without
> adding headcount for it.
>
> Worth 15 minutes to see if there's a gap between where your EDI setup is
> today and where {{retailer_name}}'s volume is about to take it?
>
> {{sender_name}}

## Template 2 — Consumer brand ops lead × compliance-policy change (signal #2)

**When to use:** same persona; signal = Tier 1 retailer compliance-policy
change (e.g. Target's Perfect Order Program), confirmed to apply to this
account (see the stacking check in `account-research-brief.md`'s
client-specific priorities).
**Proof point to use:** a chargeback-reduction stat (e.g. Liquid Death's
framing, or Orderful's own chargeback-focused blog content) — this persona
cares about margin erosion on a channel they're trying to prove out.

> **Subject:** {{retailer_name}}'s new compliance rules and {{company_name}}
>
> Hi {{contact_first_name}} — {{retailer_name}} just rolled out
> {{signal_detail}}, which applies to every current supplier, not just new
> ones.
>
> If {{company_name}}'s EDI setup isn't airtight on ASN accuracy specifically,
> this is the kind of change that turns a working setup into a new source of
> chargebacks overnight — nothing you did wrong, the bar just moved.
>
> Happy to do a quick, no-pressure look at whether this actually affects you
> before it shows up as a deduction.
>
> {{sender_name}}

## Template 3 — IT/EDI technical owner × displacement (signal #5)

**When to use:** persona = "IT/EDI technical owner at a manufacturer or
larger enterprise"; signal = public complaint pattern matching a real
displacement opportunity (unresponsive support, custom coding per partner,
unpredictable billing).
**Proof point to use:** NFI's case study ("we routinely set up new partners
within less than five days... because so many partners are already in
Orderful's network") — this persona wants technical credibility and control,
not a growth pitch.

> **Subject:** Faster trading-partner onboarding for {{company_name}}
>
> Hi {{contact_first_name}} — most EDI teams we talk to are dealing with at
> least one of: slow partner onboarding, custom mapping per connection, or
> support that doesn't move fast enough when something breaks in production.
>
> {{proof_point}}. No custom mapping, real-time transaction visibility, and
> API-first connectors to the ERPs teams like yours already run.
>
> If any of that sounds familiar for {{company_name}}, worth a technical
> walkthrough — happy to show the API and validator tool directly rather than
> just describe them.
>
> {{sender_name}}

## Template 4 — Owner/executive at smaller logistics co × capacity signal (#4 or #6)

**When to use:** persona = "Owner/executive buyer at a smaller logistics,
carrier, or 3PL company"; signal = EDI-specific job posting (#4) or new
DC/3PL/geographic expansion (#6) — both read as "we're growing faster than
our current setup handles."
**Proof point to use:** Heartland Logistics Group's case study ("Zero
Additional Headcount," 100% growth in client base) or KBX's ("if we're not
moving loads, we're not making money") — this persona thinks in revenue and
headcount, not IT features.

> **Subject:** Growing {{company_name}} without growing headcount
>
> Hi {{contact_first_name}} — {{signal_detail}} looks like {{company_name}}
> is scaling fast right now.
>
> {{proof_point}}. If onboarding a new shipper or broker relationship is
> currently the bottleneck on taking on more business, that's exactly the
> problem this solves — not another IT project, a direct way to take on more
> clients without adding people to handle it.
>
> Worth a quick call to see if the timing makes sense?
>
> {{sender_name}}

## Open gaps

- None of these four templates have been used, tested, or seen a single real
  reply — they're a starting structure built from the same public case-study
  language used throughout this repo's onboarding docs, not proven copy.
- Which proof point actually lands best per persona is a guess; real A/B
  results (once anything sends) should override the pairings above.
- No template exists yet for the "SaaS & Tech Platforms" vertical or its
  persona, since `../onboarding/persona-template.md` flagged that persona as
  unbuilt (no case-study buyer title to work from).
