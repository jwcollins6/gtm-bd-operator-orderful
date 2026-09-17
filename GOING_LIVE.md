# Going live — from demo to a rep's actual workflow

`HOW_THIS_WORKS.md` explains what this does and why. This doc is the
mechanical follow-up: the actual steps to set it up and run it, split by who
does them — ops, once, versus each rep, individually. Like the rest of this
repo, nothing here has been run for real yet; this is the plan, not a
confirmed rollout.

## Org-level setup (done once, by ops/RevOps)

1. **Connect the necessary tools.** CRM, a data enrichment source (ZoomInfo,
   Clay, Apollo, or equivalent), and any sales engagement tool already in
   use. `.env.example` already has the placeholders this needs
   (`CRM_API_KEY`, `ENRICHMENT_PROVIDER_API_KEY`) — copy it to `.env`, fill
   in real values, never commit credentials directly. Once connected,
   `business.yaml`'s `track` and `storage` fields move from `TBD` to real
   values.
2. **Set up repo access.** Reps get read-only access to the repo; only ops
   can edit the shared files (ICP, personas, signals, scoring, templates).
   This keeps everyone working off the same playbook instead of drifting
   into their own versions.
3. **Decide territory/account-routing rules**, using the CRM as the shared
   record of who's working which account — so two reps don't accidentally
   duplicate the same outreach.
4. **Turn on the automated signal-detection → research → scoring → draft
   pipeline, scheduled to run based on parameters set by the team** — see
   `skills/signal-detection-skill.md`. It depends on step 1 being done
   first, since detected candidates and their briefs need a real place to
   land.
5. **Governance sign-off.** Someone owns what "good enough to send" means
   for Orderful's brand voice, and how fast autonomy graduates from
   draft-only toward the system sending on its own (see
   `docs/eval/eval-loop.md`).
6. **Own ongoing changes to the shared playbook.** Per `score/eval-example.md`'s
   mechanism, someone periodically reviews real outcomes and decides what to
   change — a scoring weight, a signal's tier, a proof point, a threading
   approach — then edits those files directly and pushes. This is a git
   commit and push, nothing more exotic than that.

## Rep-level setup (done by each person)

1. Get a Claude Code seat.
2. Get added as a repo collaborator (read-only), clone it locally.
3. Confirm Claude Code picks up `CLAUDE.md` automatically when opened in
   that folder — it auto-loads at the start of every session.

## A rep's workflow, day to day

**The default path:** a signal fires on schedule → research, scoring, and
(for Warm/Hot accounts) a drafted sequence happen automatically, per
`skills/signal-detection-skill.md`'s chain, which stops early and logs why
for anything that fails the ICP fit check rather than fully researching a
non-fit → the rep opens their queue and reviews the finished brief, score,
and draft → edits anything that needs a human touch and sends manually,
outside this repo → logs the outcome in the CRM.

**The manual path, just as valid:** a rep can point Claude at a specific
company they noticed themselves — word of mouth, something they saw, a
referral — and run the identical research → score → draft chain on demand.
The scheduled pipeline automates the noticing; it doesn't replace a rep's
own judgment about who's worth a look.

Before each session, the rep pulls latest (`git pull`) so they're working
off the current playbook, not a stale one.

## What isn't built yet

Enforcement that reps pull latest before a session. Nothing
technical stops someone from working off an outdated clone — this needs
either a habit, a reminder, or a lightweight check, not solved here.

## Open gaps

- None of this has been run — it's a plan built from how this repo's pieces
  are designed to connect, not a confirmed rollout.
- Whether "read-only for reps, write for ops" needs an actual technical
  enforcement (branch protection, a review requirement) or just a stated
  norm is unconfirmed — depends on how much Orderful trusts the norm to
  hold versus wanting it enforced.
- Real cadence for step 6's playbook review (weekly, ad hoc, tied to a
  specific meeting) is undecided — same "no fixed cadence" posture as
  `docs/eval/eval-loop.md` itself.
