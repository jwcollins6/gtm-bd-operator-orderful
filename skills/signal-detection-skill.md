# Signal detection — skill

How to find candidate accounts for
[`../onboarding/signal-inventory-template.md`](../onboarding/signal-inventory-template.md)'s
signal types — the step before account research
(`account-research-skill.md`) or scoring (`../score/scoring-model.md`) can
run on a company. See `../docs/process/outbound-pipeline.md` stage 3
("Detect/source records") for where this fits.

A hit doesn't stop at a bare candidate — it chains straight through to a
finished, ready-to-review package. See "What a hit produces" below.

## Process, per signal type

1. **New retailer launch (#1).** Search trade press (Retail Dive, RetailWire,
   PR Newswire, WWD-type industry outlets) and press releases for "[brand]
   launches at [retailer]" coverage, filtered to major EDI-requiring
   retailers (Walmart, Target, Kroger, Costco, Home Depot, etc.). A hit needs
   a real, dated announcement — not a rumor or "in talks."

2. **Retailer compliance-policy change (#2).** Search trade press (Retail
   Dive, SupplierWiki) and retailer vendor-portal/compliance-manual updates
   for a named retailer announcing a new or changed compliance program. This
   fires once per retailer, not per company — per
   `signal-inventory-template.md`'s two-step funnel, detect the policy
   change first, then check specific candidates against it using *their own*
   public materials, not the retailer's site (see that file's Open Gaps for
   why).

3. **EDI-specific job posting (#3).** Search job boards for titles like "EDI
   Analyst," "EDI Coordinator," "EDI/Integration Engineer" at companies
   matching the ICP. **Check the job board's own terms of use before
   automating this** — the same diligence that ruled out checking Target's
   site directly applies here. If a board restricts automated/agentic
   access, this stays a manual check, the same way the compliance signal's
   retailer-site check does.

4. **Displacement complaint pattern (#4).** The hardest to automate reliably
   — it needs a complaint attributable to a *specific, already-identified*
   company, not a general pattern in competitor reviews. Best run as an
   occasional manual check (the candidate's name alongside "SPS Commerce" or
   "TrueCommerce" complaint language) once a company is already a candidate
   from another signal, not as a standalone discovery method.

5. **ERP migration/replatform (#5).** Search trade press and company press
   releases for NetSuite/SAP/Dynamics implementation announcements at
   companies matching the ICP.

6. **Funding/M&A (#6).** Search funding databases and press (Crunchbase,
   PitchBook, TechCrunch, trade press) for raises or acquisitions among
   consumer brands or logistics companies.

7. **New DC/3PL/geographic expansion (#7).** Search press for
   distribution-center openings, new 3PL partnerships, or international
   expansion announcements.

## What a hit produces

A hit chains straight through the rest of the pipeline automatically,
respecting `account-research-skill.md`'s own early-exit logic: confirm the
signal and check company basics, then run the ICP fit check *first* — if it
fails, stop there and log why (this is exactly what feeds
`../score/scoring-model.md`'s Disqualify tier), rather than spending effort
on persona mapping, a prior-relationship check, and recent-activity research
for a company that was never going to be a fit. Only a real fit continues
through the rest of the research process, then scoring, then — for anything
that scores Warm or Hot — a drafted outreach sequence via
`../templates/outreach-templates.md` and `../templates/outreach-sequence.md`.

What reaches a human for a Warm/Hot account is a finished package — brief,
score, and a ready draft sequence. That's the default flow for signals this
skill detects on schedule, not the only way in — a rep can just as easily
point Claude at a specific company they noticed themselves (word of mouth,
something they saw, a referral) and run the identical chain manually; this
skill just automates the noticing part.

## Running this on a schedule

Runs on a schedule set by the team (daily, weekly, whatever cadence fits) so
the full chain above — detection through to a drafted, ready-to-review
sequence — runs on its own, and a rep's first touch is reviewing finished
work rather than starting research themselves. Needs the org-level tool
connections (CRM/system of record) in place first, since detected candidates
and their briefs need a real place to land — see `../GOING_LIVE.md`.

## What NOT to do

The chain runs research, scoring, and drafting automatically — but never
sending. Every draft this produces is still `outbound_send: draft_only` per
`../business.yaml`; a human reviews and sends, always. Never skip a real
verification step to keep the chain moving either — e.g. signal #2's "is
this company actually carried by the retailer" check still has to happen,
using the candidate's own materials, before that signal counts as fired
(see `signal-inventory-template.md`'s Open Gaps). Never automate a
check against a site whose terms of use restrict agentic access (see
`signal-inventory-template.md`'s Open Gaps for the Target example) — check
first, don't assume a search or fetch is fine just because it's technically
possible.

## Open gaps

- Job board terms of use haven't been checked yet for signal #3,
  the way Target's were for signal #2 — flagged as a real open question, not
  assumed clean.
- Whether Orderful's own team has better sources for any of these (a paid
  intent-data feed, a specific job board they already watch) is unconfirmed
  — see `HOW_THIS_WORKS.md`'s "Signal validation, overall" item.
