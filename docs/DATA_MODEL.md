# Data model — what gets tracked, what doesn't

What the offering needs to track, in general — not where it gets stored. Storage
is a separate, per-client decision (`onboarding/storage-decision-worksheet.md`);
this doc exists so that decision has an actual spec to build against instead of
inventing the model per client.

## Reference data (lives in the repo, not here)

The ICP, verified facts, signal definitions, and governance rules built once per
client during onboarding (`onboarding/`, `governance/`) aren't part of this list —
they're prose that rarely changes and gets reviewed like any other doc. What
follows is the other kind: data that changes constantly as the system runs.

## Operational data

- **Company** — name, website/domain, industry, size, geography. The shared
  spine outbound and inbound both attach to (see `docs/DECISIONS.md` #9).
- **Person** — first name, last name, email, title/position, phone, which
  company they belong to.
- **Signals** — detected "something changed" events (see
  `docs/process/outbound-pipeline.md` stage 3), each tied to a company, with a
  type, source, and timestamp.
- **Scores** — fit × intent (outbound stage 5) or qualify result (inbound stage
  4), tied to a company/person and often to the signal that drove it.
- **Suppression** — do-not-contact list, required by `governance/README.md`,
  checked before anything else fires regardless of score.
- **Drafts** — outreach or reply drafts held for human review before sending
  (outbound stage 9, inbound respond stages).
- **Activity log** — every action actually taken: draft created, email sent,
  call logged, reply received, status changed. Matters more, not less, as
  autonomy increases — once things run non-manually, this is the only record of
  what the system actually did.
- **Routing state** — which owner/relationship a qualified or returning contact
  got sent to (inbound stage 5).
- **Eval/outcome feedback** — the manual good/bad judgment on a surfaced
  company or draft, and "meeting booked" — the same manual-marking mechanism
  answers both (`docs/eval/eval-loop.md`, `docs/DECISIONS.md` #11).

## Design principle: align Company/Person fields to common CRM shape

Define Company and Person using roughly the lowest common denominator any
standard CRM already expects (HubSpot, Salesforce, Pipedrive all want basically
this same shape). Do this on purpose, even for a client with no CRM yet — it
means mapping into whatever CRM a client actually has (now or later) is
mechanical field renaming, not a schema redesign.

## What deliberately doesn't get kept

- **Raw enrichment provider payloads** (full ZoomInfo/Clay API responses) —
  extract the fields that matter into the Company/Person record; the raw blob
  isn't queryable or useful long-term outside of debugging enrichment quality.
- **Intermediate draft attempts** — keep the version that actually got reviewed
  or sent, not every generation pass, unless there's a specific reason to study
  prompt quality over time.
