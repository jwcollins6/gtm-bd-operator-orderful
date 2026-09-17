# Eval loop

## The mechanism (decided 2026-09-04)

Feedback is **manually fed**, at least to start — John, or someone else, marking
individual leads/drafts/outcomes as good or bad. Not an automatic signal pulled
out of a CRM or calendar on its own.

The loop's job at this stage is to **surface findings for a human to act on**, not
to adjust scoring or behavior by itself. Self-adjustment is something to consider
adding later, deliberately — not the default from day one.

Spot-check review has **no fixed cadence** — weekly or ad hoc both work, whatever
fits the pace of a given client.

This same manual-feedback mechanism is also the answer to "where does 'a meeting
got booked' get confirmed from" — for both directions. It's the same person
marking the same kind of outcome, not a separate system to build.

This is a deliberate starting point, the same posture as draft-only being the
starting point for outbound sending — expected to evolve (more automatic capture,
or the loop adjusting itself) once there's a real reason to, not fixed forever.

## Two different questions, per direction

**Outbound:**
1. **Is the surfacing/data actually correct** — the right people, the right
   companies, accurate information. Foundational: if this is wrong, everything
   downstream (drafting, sending, meetings) is wasted effort. Feedback doesn't
   need to run on every record — a spot-checked sample is enough to know whether
   the system's judgment is trustworthy.
2. **How much the agent itself is allowed to do** — draft-only today; the agent
   eventually sending on its own too is the explicit goal, reached deliberately
   (crawl/walk/run) rather than all at once.

**Inbound:** question 1 (surfacing accuracy) matters less here — the person
already selected themselves in by reaching out, so there isn't the same
"did we pick the right target" risk outbound has. What matters instead is
operational: handling the work reliably (nothing dropped or missed), correctly
telling apart a genuinely new contact from a returning one (best-effort), and not
wasting a personalized response on spam/junk. That's the qualify step's job (see
`../process/inbound-process.md`), not a new mechanism. On question 2 (autonomy),
inbound can move faster than outbound for the reasons in that same doc.

## What's still open

- **Autonomy graduation criteria/thresholds** — deliberately not decided yet. The
  plan: monitor manually through the first client or two under this loop, then
  set graduation criteria from real experience rather than guessing blind now.
- Whether the loop eventually adjusts itself with less oversight, and what the
  spot-check review workflow looks like day-to-day in practice — both open,
  neither urgent; likely easier to answer once there's real data from a live
  client to look at.
