# How this works

This doc is for reading without opening every other file first — it explains
the system in plain terms: what it actually does, who does what (AI vs.
human), and what using it day to day would look like for someone on your
team. Everything it describes is built out as a concept in this repo (see
`README.md` for the file-by-file map) but has not been run for real —
nothing has been sent to anyone, and there's no engagement with Orderful yet.
This exists to make the idea concrete before that conversation happens.

## The one-sentence version

Instead of a rep starting from a blank page and a gut feeling about who to
contact, this watches for real, dated reasons a specific company needs EDI
*right now*, does the research, drafts personalized outreach to more than one
person at that company, and hands a rep a ready-to-review queue — while a
human stays in control of every message that actually goes out.

## How it actually works, end to end

**1. Something real happens.** Not "this company fits our ICP" in the
abstract — a dated, concrete event: a brand launches at a new big-box
retailer, a retailer changes its compliance rules, a company posts a job for
an EDI role, or a public complaint pattern suggests someone's current EDI
vendor is failing them. (`onboarding/signal-inventory-template.md` has the
full list, tiered by how urgent each one actually is.)

**2. The company gets checked against who Orderful actually sells to** —
industry, size, geography, and a few disqualifiers (`onboarding/icp-template.md`)
— and scored against how urgent the signal is. Fit × urgency lands the
account in a tier: **Hot** (real match, real urgency — act today), **Warm**
(worth reaching, less time pressure), **Nurture** (watch, don't act yet), or
**Disqualify** (not a fit, skip it). (`score/scoring-model.md`)

**3. A research brief gets built** — company basics, which signal fired, why
it's a fit, who at that company is likely the right contact (and a *second*
contact too, see below), and whether this company's already been touched
before. (`templates/account-research-brief.md`)

**4. Draft outreach gets written from that research** — not generic copy,
messages built from real, confirmed facts about that specific company, with
a proof point picked to match who's being contacted. (`templates/outreach-templates.md`)

**5. It's not one message, it's a paced sequence to two people.** A single
email that never gets a reply shouldn't be the end of the attempt, and a
deal shouldn't depend on reaching exactly one person. Hot accounts get a
5-step cadence (email, LinkedIn, email, phone + email, breakup) over about
two weeks, run in parallel against both a hands-on contact and a more senior
one, not sequentially. (`templates/outreach-sequence.md`)

**6. A human reviews and sends everything.** Nothing above sends itself.

**7. What actually happens gets tracked, and the system's guesses get
corrected over time** — not automatically, by a person periodically looking
at real outcomes and deciding what to change. (`score/eval-example.md`)

**One real company run through this whole chain, to make it concrete:**
`output/example-brief-true-classic.md` — True Classic (not an Orderful
customer) just launched at 460 Target stores. That's signal #1. It's a clean
ICP fit. It scores Hot. The brief identifies two contacts — an unconfirmed
ops-side person and a real, named one (CEO Ben Yahalom, already on record
about this exact partnership). Both get a full drafted sequence, written out
day by day, with every fact that isn't actually confirmed left visibly
blank rather than guessed at.

## Who does what — AI vs. human, stage by stage

This is the part worth being precise about, since it's the actual answer to
"does this replace a rep": no. It removes the blank-page problem and the
manual prioritization work. A human still makes every judgment call and
sends every message, today.

| Stage | What the system does | What a human does |
|---|---|---|
| **Spotting the signal** | Watches for the defined trigger events (retailer launches, compliance changes, job postings, complaint patterns) | Decides which signal types are actually worth watching for, and confirms new ones as they come up |
| **Scoring / prioritizing** | Applies the fit × urgency formula automatically, ranks accounts into Hot/Warm/Nurture | Sets and later adjusts the weights and thresholds behind that formula, based on what actually converts |
| **Research brief** | Pulls together company facts, checks fit, maps likely contacts, flags what's unconfirmed | Fills in or verifies anything the system couldn't confirm on its own (e.g. an actual named contact) |
| **Drafting outreach** | Writes the actual message(s) for both contacts, using real researched facts and a matched proof point | Reviews every draft, edits tone and specifics, decides whether it's good enough to send |
| **Sequencing** | Prepares each next step in the cadence in advance, so it's ready when it's time | Decides whether to continue, pause, or stop the sequence — especially the moment either contact replies |
| **Sending** | Nothing. Drafts only. | Sends every message, every time, today |
| **Logging outcomes** | Nothing automatic yet | Manually marks what happened — reply, meeting booked, or "this account shouldn't have been surfaced at all" |
| **Getting smarter** | Nothing automatic — never adjusts its own scoring or behavior | Reviews the marked outcomes periodically and decides what to actually change (a weight, a signal's tier, a proof point, whether a contact-threading approach is working) |

That last row matters: this is a deliberate, conservative starting point, not
a limitation of what's technically possible. The explicit longer-term goal
is the system eventually sending on its own too, for the cases where
confidence is earned over real results — reached deliberately, not jumped to
(see `docs/eval/eval-loop.md` and `docs/DECISIONS.md`). Today, draft-only is
the honest, correct place to start.

## How someone on your team would actually use this, day to day

Picture an AE or SDR opening this at the start of their day:

1. **A prioritized queue, not a raw list.** Hot accounts at the top, each
   with a one-line reason ("launched at 460 Target stores 2 days ago"), not
   a spreadsheet they have to make sense of themselves.
2. **Click into a Hot account and the research is already done.** Company
   facts, why it's a fit, the signal that triggered it, and — critically —
   what's *not* confirmed yet, called out explicitly rather than hidden.
3. **Two drafted sequences are sitting there, ready** — one for the
   hands-on contact, one for whoever the economic-buyer-side contact is —
   each already personalized to real facts about that company, not
   generic copy.
4. **They read it, edit anything that needs a human touch, and hit send** —
   or don't, if something looks off. This is where their judgment actually
   matters, not in writing the first draft from scratch.
5. **As replies come in (or don't), they mark the outcome.** That's the only
   new habit this asks of them — a quick, honest mark of what happened,
   which is what eventually makes the next round of prioritization and
   drafting sharper.
6. **Periodically (weekly, or whenever there's enough to look at — no fixed
   schedule), someone reviews the marked outcomes** and decides what to
   adjust — maybe a signal type isn't converting, maybe the executive thread
   isn't worth running, maybe a different proof point should be tried. Those
   changes get made deliberately, by a person, not automatically.

The practical shift for a rep isn't "an AI does my job" — it's "I stop
starting from zero on who to contact and what to say, and I spend my time on
the parts that actually need a human: judgment calls, tone, and deciding
what's worth pursuing."

## What this doesn't do (yet)

- Doesn't send anything. Every message is a draft.
- Doesn't decide on its own that a signal or scoring weight should change —
  a human always makes that call, using real outcomes as evidence.
- Doesn't have real Orderful data behind any of it yet — everything here is
  built from public research as a concept, explicitly flagged everywhere it
  appears in this repo. The next real step is a conversation, not more
  building.
