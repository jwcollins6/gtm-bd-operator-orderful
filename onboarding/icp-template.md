# ICP — Orderful

**Status: research-derived concept, not client-verified.** Built 2026-09-17
from public sources only (company-understanding-inventory.md, Orderful's own
blog, retailer EDI-compliance research, retail-trade press). Steps 1–3 below
(current customers, recently won deals, inbound leads) are not run — no access
to Orderful's real data. This is a starting hypothesis to pressure-test with
Orderful, not a finding.

## How to build this

Not a fixed checklist — these are the usual inputs, but which ones
apply, and in what order, can differ by client.

1. **Review of current customers** — **not run.** Only public marketing
   logos/case studies available (see `company-understanding-inventory.md`),
   which are curated by Orderful for marketing, not representative of the
   real base.
2. **Review of recently won deals** — **not run.** No access.
3. **Review of inbound leads** — **not run.** No access.
4. **The client's own stated understanding** — used, from their public site:
   Orderful names six verticals (Retail, Logistics/Carriers, Food & Beverage,
   Manufacturing, SaaS & Tech Platforms) and publishes their own "7 Signs You
   Need a New EDI Provider" post — read as their own stated view of buying
   triggers, even though it's marketing content, not a sales-team interview.
5. **Other sources used:** independent research into what makes an EDI
   purchase/switch happen in general — retailer compliance requirements
   (Walmart, Target, Kroger), competitor complaint patterns (SPS Commerce,
   TrueCommerce reviews on G2/Capterra), and DTC-brand-to-wholesale expansion
   coverage (Retail Dive). See `signal-inventory-template.md` for the
   detailed sourcing — this ICP is downstream of that same research.

## The ICP (fill in from the process above)

- **Industries / company types**: Two distinct shapes, not one:
  - **Consumer/CPG brands moving from DTC-only into wholesale/retail
    distribution** — need EDI specifically because a retailer now requires
    it, often for the first time. (Evidence: Caraway appears as both an
    Orderful customer logo and in 2026 retail press for a 500-store Walmart
    launch — the timing lines up with exactly this trigger.)
  - **Logistics companies, carriers, and 3PLs** — need EDI as core
    operating infrastructure (load tenders, status updates), not a
    retail-compliance afterthought; volume of trading partners scales with
    their own business growth.
  - Secondary: manufacturers and SaaS/tech platforms embedding EDI into their
    own product (Orderful names this as a vertical but it's unconfirmed as an
    actual outbound priority vs. just a covered use case).
- **Size range**: Better measured by **trading-partner count** than employee
  headcount, since that's Orderful's own pricing/segmentation axis (Enterprise
  tier = "more than 20 trading partners"). Rough read: self-serve/Web EDI fits
  a company with 1-few partners just starting compliance; Integrated fits
  companies scaling past a handful of partners with real integration needs;
  Enterprise fits 20+ partners or multi-org complexity. Revenue/headcount
  correlate loosely — case-study companies range from newer DTC brands
  (Caraway, Liquid Death) to established industrials (NFI, Bridgestone) — so
  headcount alone is a weak filter here.
- **Geography**: North America first (X12 is the core standard, matches
  Walmart/Target/Kroger-style requirements); global reach is real but newer
  (EDIFACT support added 2024) — treat non-NA prospects as valid but lower
  confidence until confirmed.
- **Buying triggers / situations (the "why now")**:
  - Just landed a new relationship with a major EDI-requiring retailer
    (biggest, most concrete trigger — see signal inventory).
  - Actively hiring for EDI-specific roles (capacity signal).
  - Visible, specific pain with a current provider (support delays, custom
    coding per partner, unpredictable billing) matching Orderful's own "7
    signs" post.
  - Mid-ERP-migration or systems replatform (NetSuite/SAP/Dynamics) — natural
    moment to reevaluate adjacent integrations.
  - Rapid trading-partner growth from funding, M&A, or channel/geographic
    expansion.
- **Disqualifiers / anti-patterns**:
  - DTC-only brand with no near-term wholesale/retail ambitions — no EDI need
    at all yet.
  - Company visibly happy with, or contractually locked into, an incumbent
    EDI provider with no public pain signal — a "looks similar" account
    (same industry/size) but no actual why-now.
  - Needs outside Orderful's supported standards/transaction scope (a real
    gap per the competitor research below — see Open gaps).
  - Single-digit lifetime trading-partner need with no growth trajectory —
    too small to be worth more than the Labels-only tier, low expansion
    potential.

## Open gaps

- Everything in steps 1–3 above (real customers, recently won deals, inbound
  leads) — the actual highest-value input, entirely missing until there's a
  real conversation with Orderful.
- Real deal-size / segment thresholds — which trading-partner-count bands
  Orderful's own sales team prioritizes.
- Whether SaaS/Tech Platforms and Manufacturing are real outbound priorities
  or just covered verticals — can't tell from the outside.
- **Competitive scope gap found during research, worth flagging directly:**
  third-party comparison content (Cleo's own competitive pages) claims
  Orderful "only supports X12 and EDIFACT" and can be a limiting choice once a
  prospect's integration needs expand past standardized EDI into broader
  file/API formats. This is competitor-authored content, not verified, but
  it's a real disqualifier pattern worth confirming with Orderful directly:
  does ICP fit narrow (as this claims) or has that scope grown?
