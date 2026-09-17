# Daily log process

After every session, write down what happened so nothing gets lost across
sessions — decisions made, threads left in progress, open questions. A running
journal, not a decisions record (`DECISIONS.md` is for settled architecture) and
not a substitute for memory — this is so anyone (John, or an agent picking this
up cold) can read one file and know exactly where things stand without
reconstructing it from scratch.

## Where entries go

Each repo keeps its own running log at `docs/DAILY_LOG.md` — the template and
every client instance. A session that touches multiple repos gets logged in
whichever repo saw the bulk of the work, not duplicated across both.

## Format

One entry per session, newest at the top. Each entry:

- **Date**
- **What happened** — brief, not a transcript
- **Decisions made**
- **Still open / next**
