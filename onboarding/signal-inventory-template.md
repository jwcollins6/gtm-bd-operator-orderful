# Signal inventory — Orderful

**Status: research-derived concept, not client-verified.** Built 2026-09-17.
Per `../docs/OFFERING_SPEC.md`, neither research nor client experience gets
trusted alone before a signal is built into detection/scoring — and the
client side hasn't happened yet. Everything below is the research half only;
the "client-verified" section is an open gap by design, not an oversight.

## Candidate signals from research

Independent research into what generally indicates buying intent/timing for
an EDI platform, informed by `company-understanding-inventory.md` and
`icp-template.md`.

1. **A brand announces a new listing/launch at a major EDI-requiring
   retailer** (Walmart, Target, Kroger, Costco, etc.) — via press release,
   retail trade press (e.g. Retail Dive), or the company's own announcement.
   This is the single most concrete "why now" available: EDI compliance is a
   hard gate on actually shipping to that retailer, usually on a real
   deadline. **Directly validated, not just theorized:** Caraway shows up
   both as a named Orderful customer (from `company-understanding-inventory.md`)
   and in 2026 retail press for launching in 500+ Walmart stores — the timing
   pattern this signal predicts actually shows up in at least one known
   Orderful customer.
2. **Company posts a job listing for an EDI-specific role** — "EDI Analyst,"
   "EDI Coordinator," "EDI/Integration Engineer," "Trading Partner
   Onboarding." A capacity signal: either their current provider isn't
   handling this for them, or in-house EDI work has outgrown their team —
   both are real pain a platform switch or first EDI purchase addresses.
3. **Public complaints about a current EDI provider matching Orderful's own
   stated pain points** — support response delays, custom coding required
   per trading partner, unpredictable per-connection billing, onboarding
   taking weeks. Sourced from G2/Capterra reviews of competitors (SPS
   Commerce, TrueCommerce) showing these complaints are real and recurring,
   and cross-checked against Orderful's own blog post ["7 Signs You Need a
   New EDI Provider"](https://www.orderful.com/blog/replace-edi-provider) —
   their own public statement of what they believe predicts a switch.
4. **ERP migration or major systems replatform announced** (NetSuite, SAP,
   Microsoft Dynamics implementation) — a natural moment to reevaluate
   adjacent integrations like EDI, since Orderful's own connectors target
   exactly these systems.
5. **Funding round or M&A activity** for a consumer brand or logistics
   company — predicts rapid trading-partner or channel expansion ahead of
   when the pain actually hits, an earlier/softer signal than #1.
6. **New distribution center, 3PL relationship, or geographic expansion**
   (especially international, now relevant given Orderful's 2024 EDIFACT
   support) — new trading-partner connections needed as a direct consequence.

## Candidate signals from the client's own experience

**Not available — no client conversation has happened yet.** The closest
public proxy is Orderful's own blog post (signal #3 above), which is their
stated view via marketing content, not verified sales-team experience of what
actually correlates with real, closed opportunities. That distinction matters
and shouldn't get collapsed — a real "client's own experience" pass needs an
actual conversation with their sales/CRO team.

## Client-verified signals

**None — open by design.** Per the offering's own discipline (see
`../docs/OFFERING_SPEC.md`), neither the research list above nor a marketing
proxy is sufficient on its own; nothing here should be built into detection or
scoring until Orderful's own team confirms which of these actually predict a
real deal, and flags anything real that's missing from this list entirely
(e.g., something only visible from inside their funnel/CRM).

## Signal tiers

Tentative, pending verification — ranked by how concrete and time-bound the
"why now" is, not by how easy the signal is to detect:

- **Tier 1 (reach out now — concrete, time-bound trigger)**
  - #1 New major-retailer listing/launch announced
  - #2 EDI-specific job posting
  - #3 Public complaint pattern matching a real displacement opportunity
- **Tier 2 (real, worth tracking, less urgent/certain)**
  - #4 ERP migration/replatform announced
  - #6 New distribution center / 3PL relationship / geographic expansion
- **Tier 3 (early/soft — context for prioritization, not a trigger alone)**
  - #5 Funding round or M&A activity

This tiering itself is a guess based on how directly each signal implies an
active, near-term need — it should be one of the first things Orderful's own
team either confirms or reorders once a real conversation happens.
