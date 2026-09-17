# Inbound process — 7 stages

Mirrors the outbound pipeline's rigor and stage-tagging convention. Two distinct
inbound failure modes motivate this: **zero response** (nobody ever answers —
usually a capacity problem) and **slow response** (someone answers, but too late —
usually a process problem). Diagnosing which one (or both) applies to a given
client is an onboarding question, not an assumption.

Grouped into four layers:

## Arrival (1-2) — event-driven, fires the moment a lead acts

1. **Capture** — unattended once built. Every inbound channel (calls, forms, SMS,
   chat, marketplace leads) lands in one place, so nothing sits scattered across
   personal phones/inboxes/spreadsheets — the direct fix for zero-response.
2. **Acknowledge** — unattended once built. An immediate auto-response fires
   before any human is involved, so a lead never goes fully dark just because a
   person wasn't free to answer.

## Understand (3-4) — reuses the same company understanding built for outbound, never a blank lookup

3. **Research/enrich** — AI-drafted-but-reviewed, and in a specific order:
   - First, and most important: is this a genuinely new contact, or an existing
     relationship (already talking to the business, or re-engaging on something
     in progress) just coming back in? Best-effort/spot-check is enough here —
     it doesn't need to be exhaustive to be worth doing. A returning contact
     skips the rest of this stage and goes straight to routing back to the
     existing relationship.
   - For someone confirmed new: check them against the shared company
     understanding and ICP first (already exists once onboarding is done for this
     client) and against the entities/signals system of record if one exists.
     External enrichment lookups are a gap-filler only — used when someone's
     confirmed new but there's too little to match against anything already
     documented.
4. **Qualify** — AI-drafted-but-reviewed. Same fit logic outbound uses to score a
   signal-detected company against the ICP, run in the other direction: does this
   self-selected contact match who this business should be selling to? Only
   applies to someone confirmed new in stage 3 — a returning contact doesn't get
   re-qualified from scratch. Before an ICP exists (a brand-new client's first
   inbound leads), fall back to a generic framework (BANT/CHAMP for most cases;
   MEDDIC/SPICED only for genuinely long, multi-stakeholder cycles) rather than
   blocking on the ICP being finished.

## Respond (5-6) — speed compounds or kills the lead here

5. **Route** — judgment-call, rule-based once built (geography, account
   ownership, deal size). For a returning contact, "routing" just means getting
   them back to whoever/wherever the existing relationship already lives.
6. **Schedule** — unattended once built. Hand the qualified lead a direct booking
   path immediately rather than a "someone will follow up" holding pattern.

## Sustain (7) — the stage most businesses skip entirely

7. **Follow up / re-engage** — judgment-call, bounded cadence (a few touches over
   1-2 weeks) for anyone who went quiet after routing or scheduling, then an
   explicit mark-cold. This is the step that keeps leads from evaporating into
   "still in someone's head, not systemized" — the original failure mode this
   whole offering exists to fix.

## Autonomy note

Inbound's autonomy trajectory can move faster than outbound's for the
genuinely-new-lead case specifically: replying to someone who opted in doesn't
carry outbound's reputation/deliverability risk, so the agent replying and
attempting to book a meeting is a reasonable, comparatively early target — it
doesn't need the same cautious crawl/walk/run pacing outbound does. See
`../eval/eval-loop.md`.
