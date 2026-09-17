# score/

Empty of real pipeline code in the template — that part is still true here.
Real scoring code gets built per client once onboarding (../onboarding/) has
determined the data platform track (A: live-connected, no custom code needed here
beyond calling the client's real tools; B: build against the system of record
chosen in storage-decision-worksheet.md) and the tech-stack audit findings. See
../docs/OFFERING_SPEC.md for why this stays a "how" decision made per client
rather than something generic here.

This instance holds two exceptions to that: `scoring-model.md` and
`eval-example.md`, both concept/rubric docs (not code), built to make the
scoring stage concrete for a pre-engagement demo — see each file's own status
note.
