# tests/

Empty in the template. Built per client once onboarding (../onboarding/) has
determined the data platform track (A: live-connected, no custom code needed here
beyond calling the client's real tools; B: build against the system of record
chosen in storage-decision-worksheet.md) and the tech-stack audit findings. See
../docs/OFFERING_SPEC.md for why this stays a "how" decision made per client
rather than something generic here.

## What would go here for Orderful

Standard tests for whatever code lands in `../ingest/`, `../enrich/`, and
`../orchestrate/` once it exists — e.g. does the job-posting parser correctly
pull company name and title from a sample listing, does a real code version
of `../score/scoring-model.md`'s table return the right tier for a known
fit/intent input, does the CRM lookup correctly flag a company that's
already in the pipeline. Nothing to test yet, since none of that code has
been written.
