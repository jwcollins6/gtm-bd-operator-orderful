# Decision audit trail

This is the running record of how `OFFERING_SPEC.md` got to where it is — kept so
a decision doesn't need to be re-litigated, and so anyone picking this project up
can see why something is the way it is, not just that it is. Where this file and
`OFFERING_SPEC.md` ever disagree, the spec wins; update this file in the same pass
as the spec whenever a new decision gets made.

## Decided (settled, don't re-litigate)

1. **Operating model** — John operates every client's instance himself at first
   (to learn); designed to be handoff-capable to the client later, with active
   training rather than just technical portability. Not sold as a self-serve
   product.
2. **Repo model** — one repo per client, forked from this general template, never
   shared/multi-tenant. Per-instance config (`business.yaml` + `.env`), no
   hard-wired personal credentials.
3. **Scope** — inbound + outbound together, in ONE repo per client, structurally
   separable inside it, not two engagements or two repos.
4. **Trigger models** — outbound = signal-driven (scheduled detection); inbound =
   event-driven (fires on arrival, not a schedule).
5. **Architecture — the two-track framework** (step 0 for any new client): does
   the client's agent have live tool access (MCP/API) to their real data
   platforms (CRM, ZoomInfo-equivalent)? Track A = live-connected, no custom DB
   needed. Track B = no live connection, build a system of record scaled to the
   client's actual size (existing CRM if usable > spreadsheet/SQLite for a solo
   operator > Postgres only once real concurrency is needed).
6. **North-star metric** — booked meetings, shared across inbound and outbound,
   refined into two layers: (1) surfacing accuracy (a human quickly confirms the
   right people/companies were found) and (2) booked meetings, the slower real
   north star.
7. **Draft-only / human-in-the-loop** — NOT a permanent design principle.
   Draft-only (human reviews and sends) is the deliberate STARTING point, with the
   agent eventually drafting AND sending as an explicit goal, reached via a
   crawl/walk/run progression per client as confidence in its accuracy is
   established. The never-fabricate-data discipline stays permanent; the
   "human must send" part is what's meant to evolve.
8. **Both processes must be explicitly documented**, not just automated — some
   clients have zero process today, not just a slow one. Outbound = 11-stage
   pipeline; inbound = 7-stage process. See `docs/process/`.
9. **Shared data model** — ICP/context research feeds BOTH directions. The
   entities/signals system of record is not outbound-only — an inbound lead
   becomes a new entity or matches one already tracked from outbound signal work,
   scored with the same fit logic either way.
10. **Onboarding** — building the ICP and connecting it to both outbound scoring
    and inbound qualification is required before either track launches, not
    outbound-first-then-retrofit-inbound-later. Onboarding also includes a
    company-understanding inventory, a signal inventory, and a tech-stack audit —
    see `onboarding/`.
11. **Eval loop feedback mechanism** — manually fed, at least to start: John or
    someone else marking individual leads/drafts/outcomes as good or bad. Surfaces
    findings for a human to act on; does NOT auto-adjust scoring or behavior on
    its own until explicitly turned on later. Spot-check review has no fixed
    cadence — weekly or ad hoc, whatever fits the client. This same mechanism is
    also the answer to where "meeting booked" ground truth comes from — same
    manual marking, not a separate system.
12. **Autonomy graduation criteria — decided to defer.** Not setting thresholds
    now. The plan: monitor manually for the first client or two, then learn and
    decide graduation criteria from real experience rather than guessing blind.

## Still open (need an actual decision, not more research)

1. **Dashboard** — deliberately deferred: the system needs to be ABLE to produce
   one (queryable underlying data); what it shows and whether inbound/outbound
   share a view is a per-client design call for later.
2. **"Build the ICP" mechanics** — is it always a full interview, or is there a
   lighter fallback for a client who won't/can't do one? Partially addressed by
   the onboarding inventories (customer/inbound/messaging/website/differentiation
   analysis, tech-stack audit) giving evidence-based inputs alongside an
   interview, but not fully resolved.
3. **Stack Industrial specifics** — the real, in-progress client build for Al
   Baron predates this template's fuller onboarding process; worth revisiting
   against the fuller inventory once this template is more settled. Separately
   still open for that instance specifically: whether to connect the ZoomInfo +
   HubSpot MCP connectors and test a live-connected approach; where lease-
   expiration data actually comes from; where draft output should land for
   review; rough scoring weights.

## Concrete build items blocked on the above

- `skills/`, `workflows/`, `ingest/`, `enrich/`, `score/`, `output/`,
  `orchestrate/`, `tests/` — scaffolded empty in this template, filled in per
  client once that client's onboarding pass (`onboarding/`) is done. Not blocked
  on any remaining "still open" item above — those items don't gate starting a
  real client instance, they're refinements to make along the way.
- Eval loop implementation — mechanism is decided (item 11 above: manual
  feedback, surface-only, spot-checked), but no actual day-to-day workflow/
  tooling exists yet to run it.
- Dashboard — no data model decided yet to build from, and deliberately not being
  designed ahead of time.
