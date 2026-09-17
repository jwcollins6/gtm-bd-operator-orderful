# ingest/

Empty in the template. Built per client once onboarding (../onboarding/) has
determined the data platform track (A: live-connected, no custom code needed here
beyond calling the client's real tools; B: build against the system of record
chosen in storage-decision-worksheet.md) and the tech-stack audit findings. See
../docs/OFFERING_SPEC.md for why this stays a "how" decision made per client
rather than something generic here.

## What would go here for Orderful

Not built, but not undefined either — this would hold the code version of
`../skills/signal-detection-skill.md`'s search process: scripts that pull raw
signal data on a schedule instead of Claude searching fresh each session.
Concretely: a script polling trade press (Retail Dive, PR Newswire) for new
retailer-launch and compliance-policy-change coverage (signals #1 and #2), a
script hitting a job board's API for EDI-specific postings (signal #3, once
that board's terms of use are actually checked — see that skill file's Open
Gaps), and a script polling Crunchbase or similar for funding/M&A activity
(signal #6). The skill file already specifies exactly what each script would
search for; what's missing is turning that into code that runs unattended
instead of an LLM reasoning through it each time.
