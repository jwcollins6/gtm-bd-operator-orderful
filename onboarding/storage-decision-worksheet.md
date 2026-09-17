# Storage decision — [Client name]

Decided by the tech-stack audit's findings, not assumed up front. Walk this in
order and stop at the first "yes":

1. **Does the client already have a working CRM or equivalent?**
   If yes -> use it. No reason to build something new alongside a tool that
   already does the job. Track = A (or B-using-existing-CRM, depending on live
   connectivity — see the tech-stack audit's "connection potential" section).

2. **Is this a genuine solo operator with light volume and simple needs?**
   If yes -> a spreadsheet (Google Sheets over a local Excel file — still
   human-editable but reachable by automation) for the simplest flat-list case,
   or SQLite when a bit more structure is needed but it's still genuinely one
   person/one process touching the data.

3. **Is there actual concurrency to support** — a team, or a client-facing
   dashboard that needs to read the same live data from a different place than
   the automation does?
   If yes -> Postgres. Not the default; only reached for once single-file/
   single-user tools would actually be a limitation.

## Decision for this client

- Track:
- Storage:
- Why (cite the tech-stack audit finding that drove this):
