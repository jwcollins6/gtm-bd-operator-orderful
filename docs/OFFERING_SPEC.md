# The gtm-bd-operator offering — what this is

Canonical spec, current as of 2026-09-04. This is the "what," not the "how" — see
each section for what's still deliberately left undecided and why.

## What this is

A service John runs for a client business: he takes over their front-end business
development — finding the right companies/people to reach out to, and handling the
people who reach out to them — and turns it from something ungoverned and
tribal-knowledge ("in their head, not systemized") into a documented, repeatable,
partly-automated system. The deliverable is the outcome (more booked meetings,
nothing falling through the cracks) plus the system that produces it — not a piece
of software sold on its own.

## Who it's for and how it's sold

Small-to-mid businesses whose growth is currently limited by disorganized business
development rather than by product or demand — a business that doesn't know how to
find the right prospects, or that lets inbound interest go unanswered or poorly
handled, because there's no defined process and no one dedicated to running one.

This is a service engagement, not a product sale. John operates the system for the
client at first — deliberately, so he learns what actually works across real
clients. But the client should ALSO be able to operate it themselves, with John's
help and training, if they want to — training/handoff is an intended part of the
offering, not just something that happens to be technically possible. Each client
gets their own independent, isolated instance — nothing shared or multi-tenant
between clients.

Exactly what training/handoff looks like, and when in a relationship it becomes
real, is deliberately left client-specific — it varies too much to generalize, and
gets decided case by case as it comes up, not designed in the abstract now.

## What it actually does

Two directions, running together for the same client, sharing the same underlying
understanding of that client's business:

**Finding prospects (outbound).** Watches for signals that a company or person is
worth reaching out to right now (not just "fits the profile" in the abstract, but
something concrete changed — e.g. a lease is expiring, a company just moved
nearby), scores how good a fit they are, and prepares research and draft outreach.
A human reviews and sends at first, but that's a starting point, not a permanent
ceiling — the explicit eventual goal is the agent handling drafting AND sending on
its own, reached deliberately (crawl/walk/run) as confidence in the system's
accuracy gets established (see `docs/eval/eval-loop.md`). Runs on its own
schedule/trigger, not tied to anyone acting first.

**Handling people who reach out (inbound).** The moment someone contacts the
business — a form fill, a call, an email — the system makes sure it's captured,
immediately acknowledged so nothing goes silent. Before anything else, it checks
whether this is genuinely someone new, or an existing relationship — already
talking to the business, or re-engaging on something in progress — just coming
back in. That distinction changes what the right response even is: a returning
contact gets routed back to whoever/whatever they were already in conversation
with, not treated as a fresh lead. Only for someone confirmed new does the rest of
the flow apply: checked against who this business should be selling to (the same
underlying understanding used for outbound) to judge fit, routed to the right
person, and followed up with on a real cadence instead of quietly going cold. This
runs the instant something happens, not on a schedule.

That identity check doesn't need to be exhaustive or guaranteed correct to be worth
having — best-effort match against whatever's actually in the system beats skipping
the check entirely and treating everyone as new by default, even knowing it'll
sometimes miss or misfire, especially early in a client relationship before much
history exists.

The autonomy trajectory for inbound is different from outbound's, and can
reasonably move faster — for the genuinely-new-lead case specifically. Since this
is someone who already reached out on their own, the eventual goal — the agent
replying directly, quickly, with a message personalized to whatever they actually
asked about, and trying to book a meeting from that reply — is comparatively
low-risk, unlike outbound's cold send to a stranger who never asked to be
contacted. Replying to someone who opted in doesn't carry the same
reputation/deliverability risk unsolicited outbound does, so inbound doesn't have
to earn agent-send autonomy at the same conservative pace as outbound. (A
returning/existing contact is a different case again — the identity check above has
already decided it's not a fresh "personalize and book a meeting" situation to
begin with.)

Both directions ultimately answer the same question — "is this person/company
worth this business's time" — using the same understanding of the business, just
triggered differently (a detected signal vs. someone showing up on their own) and
producing different outputs (a drafted outreach vs. a routed, qualified response).

## The shared foundation both directions need first

Before either direction can actually judge fit or write anything credible, a real,
deep understanding of the client's business has to exist — not just "who's a good
target" but: what they actually sell, the positioning/framing they use, the pains
their offering solves, who the buyer personas actually are (not just firmographic
fit — the actual people and what they care about), and what's already worked or not
worked in their past business development. That's the real foundation: company
understanding, of which "ICP fit criteria" is one piece, not the whole thing.

This gets built once per client, and feeds BOTH directions — the scoring/
qualification logic in each, and the actual language used in any drafted outreach
or response. It's shared infrastructure from day one, not something outbound
builds for itself that inbound borrows later.

**How it actually gets built:** not just the client's own stated understanding
taken at face value — that gets checked against real evidence and existing
material. See `onboarding/` for the concrete templates. In brief, an inventory
pass covering:

- **Current customers** — who's already bought, and what real patterns show up
  across them (size, industry, deal size, role of the buyer).
- **Recent inbound leads** — who's already been showing up on their own, showing
  both what real demand looks like and whether current positioning/messaging is
  attracting the right people or the wrong ones.
- **Existing outbound messaging** — has the client already sent outreach that
  worked (or didn't)? A direct, evidence-based starting point for what messaging/
  angle actually lands with their market.
- **Website posture** — how they currently present themselves publicly (tone,
  what's emphasized, who it seems to be talking to) — a fast, no-interview-needed
  read on current positioning.
- **Differentiation** — what the client says (or visibly shows) makes them
  different from competitors, which anything drafted later needs to actually lean
  on rather than generic category language.

The client's own interview/stated understanding is still part of this, but it's
one input alongside this independently-checked evidence, not the whole picture.

**Signal inventory:** a separate, dedicated pass specifically for building the
list of signals that mean a prospect is worth reaching out to right now. Two
sources feed candidate signals: independent research into what generally
indicates buying intent/timing for a business like this one, and the client's own
experience. Neither source gets trusted alone — the client verifies which
candidate signals are actually meaningful before any of them get built into
detection or scoring.

**Tech stack audit:** what tools/platforms the client actually uses today, and how
they're actually using them (not just what they're licensed for). This surfaces
company-understanding/process info almost for free, often uncovers capability
already being paid for but unused, and is the direct input to the storage decision
below.

**Where the data actually lives — a scaled decision, not a default:**
- If the client already has a working CRM or equivalent, use it.
- If not, scale to the client's actual size and needs: a genuine solo operator
  with light volume is well served by a spreadsheet (Google Sheets, reachable by
  automation) or SQLite (a bit more structure, still one person/one process).
- Postgres (a real, standing, multi-user database) is for actual concurrency — a
  team, or a client-facing dashboard reading the same live data from a different
  place than the automation does. Not the default; reached for once
  single-file/single-user tools would actually be a limitation.

For content gaps on a new or small client: note explicitly what's missing, use
whatever real material does exist, and fill gaps with independent research — never
fake it.

## What "working" looks like

Booked meetings is the ultimate north star, but not the only signal of value: if
the system surfaces the right people/companies at all — and a human confirms
those are real, correctly-identified, actually-a-fit prospects — that's a win in
its own right, and an earlier, faster signal than waiting for a meeting to get
booked. So there are two layers: (1) is the system finding/surfacing the right
people at all — verifiable quickly, by a human confirming yes/no on what got
surfaced — and (2) does that ultimately lead to booked meetings, the real,
slower-moving north star.

The system should get better at its job over time by learning from real outcomes
(both layers), not run on a static, never-updated formula. See
`docs/eval/eval-loop.md` for the current, decided shape of that loop, and for what
about it is still deliberately left open.

A client-facing dashboard is part of this eventually. The near-term requirement is
just that the system needs to be ABLE to produce one when it's time (the
underlying data needs to exist and be queryable) — not that its exact layout or
contents get decided now. What it actually shows gets figured out per client,
based on what they care about and what data is genuinely available for them.

## What this spec deliberately does NOT decide

This describes what the offering is, not how it gets built. No decision here
about: what software/technical architecture runs it, what file or folder structure
a client instance has beyond this template's starting shape, which parts are
custom code vs. an AI agent following instructions vs. a human doing it manually,
or how any given client's specific tools get connected. Those are real decisions
that matter, but they're downstream of this spec being right.

## Deliberately left client-specific / decide-later-not-now

- Exactly what training/handoff to a client involves, and when in the relationship
  it becomes real — decided case by case, not generalized here.
- What a client-facing dashboard actually shows, and whether inbound/outbound get
  one combined view or separate ones — a per-client design decision for later.
- Autonomy graduation criteria/thresholds (crawl-walk-run), for both directions —
  deliberately not set yet. The plan is to monitor manually through the first
  client or two under the eval loop's manual-feedback mechanism, then set
  graduation criteria from that real experience rather than guessing at thresholds
  with no data. See `docs/eval/eval-loop.md`.
