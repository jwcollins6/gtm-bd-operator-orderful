# Onboarding meeting checklist

A live-meeting script, not a document to fill in during the call. Run this
conversation, then afterward transcribe what you learned into the actual
onboarding files (`company-understanding-inventory.md`, `icp-template.md`,
`persona-template.md`, `signal-inventory-template.md`,
`tech-stack-audit-template.md`) — each section below says which file its
answers feed.

Budget 60–90 minutes for a first pass. It's fine to split across two calls —
better to get real answers than rush a checklist.

## Before the meeting

Do a quick pass on their public site and any existing materials first (see
"Website posture" below) — arriving with a few observations already in hand
makes the meeting a conversation, not an interrogation, and lets you ask "is
this actually right?" instead of "what do you do?"

## Opening — frame it (5 min)

Say up front what this is and isn't: you're building a system that finds the
right prospects and handles inbound leads, starting from a real, evidence-based
understanding of their business — not a generic template. Everything it
produces gets reviewed by them before anything goes out, at least at first —
that's a deliberate starting point, not a limitation. Set the expectation that
some answers will be "I don't know" or "we don't track that" — that's a real,
useful finding, not a failure to prepare.

## Part 1 — company understanding (15–20 min)

Feeds `company-understanding-inventory.md`.

- **"Who are your best customers today, and what do they have in common?"** —
  why: real patterns across the base beat a stated ICP nobody's checked against
  reality.
- **"Walk me through a deal you're proud of winning — how did it actually come
  together?"** — why: concrete, not aspirational; this is also input #2 for the
  ICP below.
- **"Who's reached out to you on their own recently — cold, no relationship?"**
  — why: shows what real demand looks like, and whether current positioning
  attracts the right people or the wrong ones.
- **"Have you sent outreach before? What worked, what didn't?"** — why: a
  direct, evidence-based starting point instead of guessing at messaging from
  scratch.
- **Website posture** — don't ask this one live; note it from your own look
  beforehand, then confirm: "I noticed your site emphasizes X — is that still
  how you'd describe yourselves?"
- **"What do you think actually makes you different from competitors?"** — why:
  whatever gets drafted later needs to lean on this, not generic category
  language.

## Part 2 — building the ICP (15 min)

Feeds `icp-template.md`. This is a synthesis step, not just more questions —
you're checking Part 1's answers against each other, not collecting new raw
material.

- Review what came out of "current customers" and "recently won deals" above
  for real patterns: industry, size, geography, buying trigger.
- **"What's the actual trigger — what has to be true or just changed for
  someone to need you right now?"** — why: this is the "why now," the thing
  that turns a fitting company into an active prospect.
- **"Are there companies that look like a great fit on paper but actually
  aren't? What's different about them?"** — why: disqualifiers matter as much
  as the fit criteria — easy to skip, worth deliberately asking.
- **"How would you describe this to someone who's never heard of your
  business?"** — the client's own stated understanding — one input, not the
  whole picture, checked against everything above rather than taken at face
  value.

## Part 3 — personas (10 min)

Feeds `persona-template.md`. Different roles need different messaging — don't
skip this even if it feels like it overlaps with Part 2.

- **"Who's actually the decision-maker, and does that change by company
  size/type?"** — why: the buyer often isn't one fixed role across every deal.
- For each persona named: **"What does that person actually care about? What
  makes them say no?"** — why: this is the part that's almost always skipped,
  and the part that actually determines whether a draft sounds specific or
  generic.

## Part 4 — signals (15 min)

Feeds `signal-inventory-template.md`.

- **"Before someone ever reaches out, what usually tips you off that they're
  about to be in-market?"** — why: this is the outbound engine's whole premise
  — something concrete changed, not just "fits the profile." Get their own
  words, don't paraphrase into something blander.
- **"Is there a data source behind that, or is it something you just notice/
  remember?"** — why: distinguishes a sourceable signal from private knowledge
  that lives in the client's head. Flag anything with no clear source as an
  access question for later, don't let it block the rest of the meeting.
- **"What would you want automated that you don't have time to do manually
  today?"** — why: often surfaces a real wishlist signal nobody would think to
  ask about directly.
- **"How do you feel about false positives — would you rather see more and
  filter yourself, or fewer and more precise?"** — why: this directly sets
  scoring posture later; don't assume precision is always preferred.

## Part 5 — tech stack & tools (10 min)

Feeds `tech-stack-audit-template.md`, which directly feeds
`storage-decision-worksheet.md`.

- **"What do you use today for finding people, sending outreach, and tracking
  it — CRM, sequencing tool, calling tool, anything else?"**
- For each tool: **"How do you actually use it day to day?"** — not what
  they're licensed for. This is often where the real process gets revealed
  almost for free.
- **"Do you know if [tool] has an API, or is everything through the
  dashboard?"** — why: this is the connection-potential question that
  determines whether automation is even technically possible yet — don't skip
  it just because it's a more technical question than the rest of the meeting.

## Part 6 — governance & guardrails (5 min)

Feeds `governance/README.md`'s client-specific section and `business.yaml`'s
`autonomy` block.

- **"Is there anyone we should never contact — existing customers, a
  competitor, anyone who's asked not to be reached?"** — why: a suppression
  list exists before any real outreach drafting starts, not after.
- **"How involved do you want to be reviewing things before they go out, at
  least at first?"** — why: sets expectations that draft-only is the default
  starting point, regardless of how much they already trust the system.

## Wrap-up & next steps (5 min)

Say plainly what happens next: you'll write up what you heard, flag anything
that's still an open gap rather than guessing at it, and come back with
specific follow-up questions rather than a finished system. Set a rough
timeline if you have one. End by confirming: is there anything about how your
business actually works that this conversation didn't get to?

## After the meeting

Transcribe answers into the real onboarding files (not this checklist — it
stays a reusable script, never client-specific content). Anything you couldn't
get a real answer to goes in that file's own "Open gaps" section, not filled
with a guess. If real gaps remain, a short follow-up conversation is a normal
next step, not a sign the first meeting went badly.
