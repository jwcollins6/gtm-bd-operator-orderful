# enrich/

Empty in the template. Built per client once onboarding (../onboarding/) has
determined the data platform track (A: live-connected, no custom code needed here
beyond calling the client's real tools; B: build against the system of record
chosen in storage-decision-worksheet.md) and the tech-stack audit findings. See
../docs/OFFERING_SPEC.md for why this stays a "how" decision made per client
rather than something generic here.

## What would go here for Orderful

Once a CRM and enrichment source are connected (see `../GOING_LIVE.md` item
1), this would hold the API integration code that replaces the manual/LLM-
driven lookups `../skills/account-research-skill.md` currently has to do by
searching: a ZoomInfo/Clay/Apollo API call that takes a company name and
returns employee count, industry, and named contacts — directly resolving
the "named contact: unconfirmed" gap that shows up in every persona mapping
in this repo (see `../output/example-brief-true-classic.md` for what that
gap looks like today) — and a CRM API call that checks whether a company is
already in the pipeline, replacing the manual prior-relationship check with
a lookup. Not built because no enrichment source or CRM is connected yet.
