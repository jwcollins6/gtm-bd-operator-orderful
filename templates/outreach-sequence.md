# Outreach sequence — Orderful

**Status: research-derived concept, not client-verified.** Built
2026-09-17. `outreach-templates.md` defines individual messages; this is the
missing piece — outbound-pipeline.md stage 9 ("Sequence outreach") isn't one
message, it's a cadence of several, across channels, spaced over time. Every
step is still a **draft** per `business.yaml`'s `outbound_send: draft_only` —
a human decides whether and when each one actually goes, this doesn't change
that, it just prepares the next step in advance so the human isn't starting
from a blank page each time.

## Which sequence to use

Pace and length should follow the score tier from `../score/scoring-model.md`,
not be the same for everyone:

- **Hot** — compressed, ~2 weeks, 5 touches (below). The signal behind a Hot
  score is usually itself time-bound (a retailer launch, a compliance
  deadline) — the "why now" decays if outreach drags on for a month.
- **Warm** — same 5 touches, stretched to ~4 weeks. Less urgency to justify a
  fast cadence.
- **Nurture** — no sequence yet. Per the scoring model, Nurture accounts get
  logged and watched for a second signal to fire, not sequenced.

## Hot-tier sequence (5 steps)

| # | Day | Channel | Purpose | Ask |
|---|---|---|---|---|
| 1 | 0 | Email | Open with the signal itself — the reason this is timely | Soft: 15 min to talk |
| 2 | 3 | LinkedIn | Second surface, proves a real person not a blast; adds one more proof point | None — just visibility/connection |
| 3 | 6 | Email | Angle switch: growth → risk/compliance, using whatever the brief's "does the compliance signal also apply" check found | Soft: quick no-pressure look |
| 4 | 10 | Phone + follow-up email | Channel switch; voicemail if no answer, short email referencing the call attempt with a specific case study link | Direct: pick a time |
| 5 | 14 | Email (breakup) | Low-pressure exit — stop the cadence, leave the door open | None — explicitly closes the loop |

Each step's actual copy still comes from `outreach-templates.md`'s persona ×
signal templates (step 1 = whichever Template 1-4 matches; step 3 reuses
Template 2's compliance angle *if* that signal is confirmed for this account,
otherwise stays on the original angle) — this file sequences and paces them,
it doesn't replace them.

**If a second, stronger signal fires mid-sequence** (e.g. the compliance
check in step 3 comes back confirmed after step 1 already went out), that's
the scoring model's stacking case — worth pulling the account out of the
default pace and accelerating, not waiting for day 6 to react to something
already known.

## Step 2 and step 4 detail (not full email templates, since they're shorter/different-channel)

- **Step 2 (LinkedIn, Day 3):** connection request + one-line note
  referencing the email sent 3 days earlier and one additional stat not used
  in step 1, to avoid repeating the exact same pitch on a second channel.
- **Step 4 (Phone, Day 10):** voicemail script mirrors the email's opening
  hook (the signal), states one proof point verbally, and says a follow-up
  email with a specific link is coming — so the email that follows isn't a
  cold restart.

## Multi-threading — running two contacts, not one

Per `../onboarding/persona-template.md`'s multi-threading section, a **Hot**
account shouldn't run this sequence against a single contact — one person
going dark (wrong contact, changed roles, just busy) shouldn't be able to
kill the whole account. For a Hot account, run the same 5-step cadence
against **both** the primary persona and its paired second contact, in
parallel, not sequentially:

- **Same timeline, offset by a couple of days** — e.g. primary contact starts
  Day 0, second contact starts Day 2 — rather than fully synchronized (looks
  more like two separate people reaching out than one coordinated blast) or
  fully sequential (waiting for one thread to fail before starting the
  other, which defeats the point of threading in parallel at all).
- **Different angle per contact, not the same email twice** — the primary
  persona's champion-side angle (per `outreach-templates.md`) vs. the second
  contact's cost/risk/approval angle. Sending the identical email to two
  people at the same company reads as spam, not as thorough outreach.
- **A reply on either thread should affect the other** — if the second
  contact (say, the economic buyer) replies first, that's worth pausing or
  adjusting the primary thread's remaining steps around, not running both
  blindly to completion regardless of what's already happened.
- **Warm accounts:** thread if a second contact is easy to identify, but
  don't hold up outreach hunting for one — Hot is where multi-threading is
  the default, not optional.
- **An executive-level second contact usually gets a shorter, lower-frequency
  version of this cadence** (e.g. 3 touches over the same ~2 weeks, not 5) —
  not an identical copy of the primary contact's pace. Executives get fewer,
  higher-signal touches in practice; see the True Classic worked example for
  what that looks like applied.

Which second contact to actually thread for a given account (name, title)
is answered per-account in `../templates/account-research-brief.md`'s
persona-mapping section, which now asks for both contacts on Hot accounts —
not something this file decides in the abstract.

## Open gaps

- This cadence (5 touches, 2 weeks, this channel mix) is a generic B2B outline
  adapted to this signal's urgency — not derived from anything Orderful's own
  sales team has found to actually work. Real reply-rate data per step, once
  anything sends, should reshape this before it's trusted.
- Whether LinkedIn is even a channel Orderful's sales team uses today is
  unconfirmed — this assumes it because it's standard practice, not because
  it's been verified for this client.
- No sequence exists yet for Warm's exact pacing beyond "same steps, slower"
  — the actual spacing (weekly? biweekly?) is a guess.
- Multi-threading mechanics above (offset start, reply-triggers-reassessment)
  are standard B2B sales practice, not something proven for this specific
  client or product — how much genuine coordination this needs versus just
  "reach two people" is unconfirmed.

## Worked example

See [`../output/example-brief-true-classic.md`](../output/example-brief-true-classic.md)
for this sequence's 5 steps filled in for True Classic (Hot tier), now
including a second, parallel thread to a named secondary contact.
