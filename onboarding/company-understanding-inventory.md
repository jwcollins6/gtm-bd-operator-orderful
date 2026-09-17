# Company understanding inventory — Orderful

**Sourcing note:** built 2026-09-17, entirely from Orderful's own public
website (orderful.com — homepage, pricing, "Our Story," case study pages) and
their public G2 presence. No access to Orderful's actual CRM, customer list,
inbound funnel, or internal sales messaging — this is a demo built to show
Orderful's CRO (Mike Head) the offering, not a completed onboarding pass. The
"Content gaps" section at the bottom is not boilerplate here — it's the real
list of what would need to come from Orderful directly before any of this
counts as settled.

## Current customers

Not knowable from public sources — no access to Orderful's actual customer
list or deal data. What's public is a set of named logos and case-study
customers, which is evidence of the *kind* of company Orderful sells to, not a
verified account of "who's already bought" or deal-size patterns:

- **Brands / retail / CPG:** Liquid Death, Caraway, Oura Ring, Hu Kitchen,
  Pabst, G-III
- **Logistics / carriers / 3PL:** NFI, Hirschbach, Bridgestone, KBX Technology
  Solutions, Heartland Logistics Group
- **Food & beverage / manufacturing:** Aurora Organic Dairy, Grosfillex North
  America
- **Fulfillment / tech:** ShipBob

Named buyer titles from their own case studies (a proxy for who owns
the relationship, not a verified persona list): Business Applications Manager
(Liquid Death), President of Integrated Logistics (NFI), EDI Team Leader (KBX),
IT Manager (Grosfillex), President (Heartland Logistics Group).

Pattern visible from this alone: spans mid-market consumer brands doing retail
EDI compliance up through smaller logistics/carrier companies where EDI
connectivity is closer to revenue-critical infrastructure than back-office
plumbing — real segmentation (size, deal size, expansion pattern) is unknown.

## Recent inbound leads

Not knowable from public sources — this is internal funnel data (demo
requests, who's filling out "Book a Demo," what they're asking about). Open
gap, not something independent research can substitute for.

## Existing outbound messaging

Not knowable from public sources — this is Orderful's own sales team's
outbound cadences/messaging, distinct from their public-facing marketing copy
below. Open gap.

## Website posture

Confident, contrarian-toward-legacy-EDI tone throughout. Framing is explicitly
against the traditional EDI vendor/VAN model: "Most services sell you EDI
connections on a one-by-one basis because keeping you on the hook is how they
make money" — positioned as the alternative to being locked into a slow,
per-connection billing relationship.

Speed is the dominant emphasis, repeated at every level: "Taking EDI from 90
Days to 90 Seconds" (company tagline), "10x Faster EDI Implementations,"
"Onboard partners in days," "Stop Mapping. Start Trading." Site leans heavily
on quantified proof over description — every case study leads with hard
numbers (70% cost reduction, <5 days to onboard, 90% less chargebacks) rather
than qualitative claims, and G2 "Leader" / "Momentum Leader" / "High
Performer" badges are surfaced prominently on the homepage itself, not buried
on a separate reviews page.

Site is structured around two buyer motions simultaneously: a self-serve path
with transparent, published pricing (unusual for enterprise EDI, which is
typically custom-quote-gated) starting at $99-189/month, alongside an
enterprise/custom tier gated behind "Talk to an Expert." Talks to both a
technical/ops buyer (API docs, integrations, a public EDI glossary and
real-time validator tool) and a business buyer (chargeback reduction, revenue
impact, "Zero Additional Headcount" as a stated outcome).

## Differentiation

Positioned against two things at once: (1) legacy EDI VANs/consultancies that
profit from slow, per-connection, one-by-one setup, and (2) the general pain
of custom EDI mapping work eating engineering time.

Core differentiator claimed is network effects: "10,000+ trading partners"
already connected means a new customer isn't starting from zero — onboarding a
new partner is mostly a matter of joining an existing network rather than
building a new integration from scratch. This is the direct explanation given
for the speed claims (case studies cite this explicitly: NFI's onboarding
speed is attributed to partners already being in Orderful's network).

Secondary differentiators: an AI-powered mapping layer (Mosaic) that claims to
eliminate manual EDI mapping work entirely for ERP-integrated customers; a true
self-service, no-EDI-expertise-required tier (Pixel) for trading partners too
small to justify their own EDI investment; transparent published pricing
across three of four tiers, unusual for the category.

## What they sell / positioning / pains solved / buyer personas

**What they sell:** A unified EDI trading platform with three product lines —
Mosaic (API-based, ERP-integrated EDI with AI-assisted mapping), Pixel (web-
form EDI for trading partners with no EDI expertise or system integration),
and Shipping Labels (UCC-128/GS1 compliant label generation). Also sells
managed services (fully outsourced EDI operations), integration services, and
two workflow-specific offerings — Order-to-Cash and Procure-to-Pay.

**Positioning:** "The last EDI integration you'll ever need" — a modern,
API/AI-native alternative to legacy EDI middleware and VANs, sold on speed and
network reach rather than feature-by-feature comparison.

**Pains solved (as stated/implied):**
- Trading-partner onboarding taking weeks to months (case studies cite going
  from 6 months to 1 month, or to under 5 days)
- EDI-related chargebacks from retail partners for non-compliance
- Engineering time sunk into custom, per-partner EDI mapping
- Lack of real-time visibility into transaction/order status
- Being technically excluded from EDI-requiring trade relationships because a
  company is too small to justify traditional EDI investment (Pixel's target)

**Buyer personas (inferred from case-study titles, not verified):**
- **Hands-on technical/ops owner** — IT Manager, Business Applications
  Manager, EDI Team Leader — likely the day-to-day owner and probable initial
  evaluator, more common at mid-market+ brands and manufacturers.
- **Owner/executive buyer** — President, President of Integrated Logistics —
  seen specifically at smaller logistics/carrier/3PL companies, where EDI
  connectivity is closer to revenue infrastructure than IT overhead, so the
  buyer sits higher in the org.

**Industries served (as named on site):** Retail, Logistics/Carriers & 3PLs,
Food & Beverage, Manufacturing, SaaS & Tech Platforms (embedding EDI into
their own products via API).

**Company facts (context, not ICP):** Founded 2017 by CEO Erik Kiser, HQ San
Francisco. Raised seed ($2M, Initialized Capital, 2019), Series A ($10M, a16z,
2020), Series B ($20M, GLP Capital Partners, 2022). Leadership: Piers
MacDonald (CTO), Sam Gorman (CFO), Mike Head (CRO), Ashwath Kirthy Vasan (VP
Product), Nikki Stephens (VP Customer Operations), Stephanie Blakey (VP
People).

## Content gaps

Everything above comes from Orderful's own public marketing site, not from
Orderful directly, so treat the whole document as a hypothesis set, not a
finding set. Specifically missing, and not fillable by more public research:

- Real customer list and segmentation (size, industry mix, deal size,
  expansion vs. new-logo mix) — the logos/case studies above are
  marketing-selected, not representative.
- Recent inbound lead volume/quality and what it says about current
  positioning's actual pull.
- Existing outbound sales messaging/cadence their own SDR/AE team runs today,
  and what's worked or not.
- Which of their four pricing tiers (Labels / Web EDI / Integrated /
  Enterprise) maps to which target segment in practice, and real deal-size
  ranges.
- Whether "SaaS & Tech Platforms" (an Orderful vertical on their own site) is
  a priority target for their outbound motion, or just one of six
  verticals listed for coverage.

This document should be revisited (or rebuilt from scratch with real input)
the moment an actual conversation with Orderful happens — it exists to make
the pitch concrete, not to stand in for the real onboarding pass described in
`onboarding/README.md`.
