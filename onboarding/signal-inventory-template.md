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
2. **A major retailer tightens or changes its EDI/vendor compliance
   program** — a new fine structure, new mandatory transaction-accuracy
   requirement, or new compliance deadline announced by the retailer itself.
   This works differently from every other signal here: it isn't
   per-company, it's a single macro event that instantly raises real,
   dollar-denominated risk for *every current supplier of that retailer* —
   including ones with a perfectly stable EDI setup today, since the bar
   moved under them, not because they did anything wrong. **Concrete, dated
   example, not hypothetical:** Target's "Perfect Order Program" (introduced
   May 2025) added three new automated compliance layers — ASN Availability,
   ASN Accuracy, and Physical Barcode Accuracy — each carrying a $0.75-per-
   carton fine with a $100 minimum, and a single bad shipment can now trigger
   several of these at once. Nothing the supplier changed; the enforcement
   changed. **Validation note:** Orderful's own marketing already targets
   this exact moment — they publish a dedicated ["Target EDI Requirements:
   Complete Vendor Compliance Guide
   (2026)"](https://www.orderful.com/blog/target-edi-requirements) post, and
   sponsored a Retail Dive piece (Aug 2026) titled ["Why Retailers Are Making
   EDI Compliance Non-Negotiable for Vendors in
   2026"](https://www.retaildive.com/spons/why-retailers-are-making-edi-compliance-non-negotiable-for-vendors-in-2026/827304/)
   — real evidence their own team already treats a retailer's compliance-
   policy change as a buying moment, not just a plausible-sounding theory.
   **Detection approach is genuinely different from the rest of this list**:
   not found one company at a time — it starts from monitoring retailer-side
   compliance-manual updates and trade press (Retail Dive, SupplierWiki) for
   the policy change itself, then crosses that against a list of the
   retailer's known suppliers (built from press releases, trade-show
   exhibitor lists, LinkedIn, or public supplier directories) to generate a
   whole batch of high-confidence, urgently-timed targets from one event,
   rather than discovering them individually. That supplier-list-building
   step is a real operational cost this signal specifically requires — see
   Open gaps below.
4. **Company posts a job listing for an EDI-specific role** — "EDI Analyst,"
   "EDI Coordinator," "EDI/Integration Engineer," "Trading Partner
   Onboarding." A capacity signal: either their current provider isn't
   handling this for them, or in-house EDI work has outgrown their team —
   both are real pain a platform switch or first EDI purchase addresses.
5. **Public complaints about a current EDI provider matching Orderful's own
   stated pain points** — support response delays, custom coding required
   per trading partner, unpredictable per-connection billing, onboarding
   taking weeks. Sourced from G2/Capterra reviews of competitors (SPS
   Commerce, TrueCommerce) showing these complaints are real and recurring,
   and cross-checked against Orderful's own blog post ["7 Signs You Need a
   New EDI Provider"](https://www.orderful.com/blog/replace-edi-provider) —
   their own public statement of what they believe predicts a switch.
6. **ERP migration or major systems replatform announced** (NetSuite, SAP,
   Microsoft Dynamics implementation) — a natural moment to reevaluate
   adjacent integrations like EDI, since Orderful's own connectors target
   exactly these systems.
7. **Funding round or M&A activity** for a consumer brand or logistics
   company — predicts rapid trading-partner or channel expansion ahead of
   when the pain actually hits, an earlier/softer signal than #1.
8. **New distribution center, 3PL relationship, or geographic expansion**
   (especially international, now relevant given Orderful's 2024 EDIFACT
   support) — new trading-partner connections needed as a direct consequence.

## Candidate signals from the client's own experience

**Not available — no client conversation has happened yet.** The closest
public proxy is Orderful's own blog/sponsored content (signals #2 and #5
above), which is their stated view via marketing content, not verified
sales-team experience of what actually correlates with real, closed
opportunities. That distinction matters and shouldn't get collapsed — a real
"client's own experience" pass needs an actual conversation with their
sales/CRO team.

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
  - #2 Retailer tightens/changes its EDI compliance program (macro event —
    generates a batch of targets per occurrence, not one at a time)
  - #4 EDI-specific job posting
  - #5 Public complaint pattern matching a real displacement opportunity
- **Tier 2 (real, worth tracking, less urgent/certain)**
  - #6 ERP migration/replatform announced
  - #8 New distribution center / 3PL relationship / geographic expansion
- **Tier 3 (early/soft — context for prioritization, not a trigger alone)**
  - #7 Funding round or M&A activity

This tiering itself is a guess based on how directly each signal implies an
active, near-term need — it should be one of the first things Orderful's own
team either confirms or reorders once a real conversation happens. Signal #2
is tiered highest despite being the hardest to detect (see Open gaps below)
because when it fires, it doesn't just predict one deal — it identifies a
whole wave of newly-urgent prospects at once, tied to a real dollar figure
(e.g. Target's $0.75/carton fines) rather than an inferred pain point.

## Open gaps

- **Signal #2's real cost is building and maintaining retailer→supplier
  lists**, not spotting the policy change itself (that part's just trade-press
  monitoring). Knowing "Target changed its compliance program" is useless for
  outbound without a reasonably current list of who supplies Target — that
  list doesn't exist yet and would need real work (press releases, trade-show
  exhibitor data, LinkedIn, public supplier directories) to build per retailer,
  and it decays over time as supplier relationships change.
- Whether this document's asserted facts (Target's Perfect Order Program
  terms, the specific fine amounts) hold up under closer scrutiny than a web
  search — worth a direct check against Target's actual current vendor
  compliance manual before this gets used in front of anyone at Orderful.
- No client-side confirmation yet for any signal, including this one — see
  "Client-verified signals" above.
