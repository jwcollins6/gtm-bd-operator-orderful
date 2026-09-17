# Outbound pipeline — 11 stages

Documented at this level of rigor so the process is explicit even before any of it
is automated. Each stage is tagged with how it's expected to run once built:
**unattended** (no human needed), **AI-drafted-but-reviewed** (agent prepares,
human reviews/acts), or **judgment-call** (a human decides, agent may assist).

Grouped into three layers:

## Data Foundation (1-4)

1. **Scope the bottleneck** — judgment-call. Confirm, for this client, that
   business development (not product or demand) is actually the growth
   constraint, and which side of it (finding people, handling people who
   reach out, or both) needs the most attention first.
2. **Define signal tiers by urgency** — judgment-call, informed by the signal
   inventory (`../../onboarding/signal-inventory-template.md`). Not every signal
   means "reach out today" — tier them so scoring and outreach timing reflect how
   urgent a given signal actually is.
3. **Detect/source records** — unattended once built. Covers two different
   circumstances, not just one: sometimes there's already a known list of
   accounts to monitor (client-provided, or one that falls out of something
   else happening — e.g. an active listing creating its own targeting radius);
   other times there's no starting list at all, and this stage has to find new
   accounts by querying signal + ICP criteria directly. Not two rigid,
   separately-built paths — just make sure whatever gets built here can take
   either kind of input.
4. **Enrich** — AI-drafted-but-reviewed. Fill in the information needed to
   qualify and personalize outreach, cheapest-reliable-source first, escalating
   to more expensive lookups only when needed.

## Data Modeling (5-7)

5. **Score fit x intent** — AI-drafted-but-reviewed. Combine ICP fit (from the
   shared company-understanding foundation) with how strong/recent the signal is,
   sorting into something like sales-ready / nurture / awareness tiers.
6. **AI-drafted account research** — AI-drafted-but-reviewed. Prepare the context
   a human (or eventually the agent) needs to write something specific, not
   generic.
7. **Verify / quarantine low-confidence data** — judgment-call. Anything the
   system isn't confident about gets held back rather than reaching a draft or a
   rep as if it were solid — never fabricate or guess and present it as fact.

## Data Activation (8-11)

8. **Route by score** — unattended once built. Higher-tier prospects get
   attention (or automation) sooner.
9. **Sequence outreach** — starts AI-drafted-but-reviewed (human sends); the
   explicit eventual goal is the agent sending on its own too, reached via
   crawl/walk/run (see `../eval/eval-loop.md`), not jumped to.
10. **Classify replies / sync CRM (or system of record)** — unattended once
    built.
11. **Measure signal-to-meeting rate by signal type** — judgment-call, this is
    the outbound half of the eval loop (`../eval/eval-loop.md`). Decide per
    signal type whether to invest more, maintain, or defund it, based on real,
    manually-reviewed outcomes.
