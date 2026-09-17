# Personas — Orderful

**Status: research-derived concept, not client-verified.** Built 2026-09-17
from case-study buyer titles on orderful.com plus general reasoning about how
each company type would actually experience an EDI buying decision. No sales
team input, no customer interviews. Treat as a starting hypothesis.

## Personas

### Ops/Systems lead at a consumer brand entering retail

- **Title(s)**: Business Applications Manager, Operations Manager, Supply
  Chain Manager, VP of Operations (title varies more at this company size than
  at larger enterprises — evidenced by Liquid Death's "Business Applications
  Manager" case study).
- **Which company segment they map to**: Consumer/CPG/DTC brands moving into
  wholesale or big-box retail for the first time or expanding it (Caraway,
  Liquid Death, Oura, Hu Kitchen-type companies).
- **What they care about / priorities**: Not missing the retailer's go-live
  date — EDI compliance is a hard gate on actually shipping to a new retail
  partner. Not having to hire a dedicated EDI specialist just to handle one or
  two retail relationships. Avoiding chargebacks that eat margin on a channel
  they're trying to prove out.
- **Messaging angle that resonates**: Speed and simplicity over technical
  depth — "go live with this retailer in days, not months," "own the keys to
  the kingdom" (Liquid Death's own quoted language) rather than depending on
  an outside EDI consultant they don't have visibility into.
- **Common objections**: "We don't have anyone in-house who understands EDI"
  (Pixel's no-expertise-required angle directly answers this); cost relative
  to a still-small wholesale channel; uncertainty about whether this retail
  relationship will even scale enough to justify a platform investment.
- **Channel/format preference**: Likely responsive to case studies from
  peer DTC brands (social proof from a company they recognize) more than
  technical documentation.

### IT/EDI technical owner at a manufacturer or larger enterprise

- **Title(s)**: IT Manager, EDI Team Leader, EDI Analyst/Coordinator,
  Integration Engineer (evidenced by Grosfillex's "IT Manager" and KBX's "EDI
  Team Leader" case studies).
- **Which company segment they map to**: Established manufacturers, larger
  retail suppliers, and companies with a real IT/integration function
  managing EDI as one system among several (ERP, WMS, TMS).
- **What they care about / priorities**: Reducing manual firefighting —
  custom mapping work per trading partner, chasing failed transactions,
  being the bottleneck when the business wants a new partner connected.
  Transaction visibility and reliability (uptime, error tracing) matter more
  here than at a smaller brand, since this person owns the incident when
  something breaks.
- **Messaging angle that resonates**: Technical credibility and control —
  "connect once, no custom mapping," real-time transaction visibility, API-
  first integration with the ERPs they already run (NetSuite, SAP, Dynamics).
  Directly addresses Orderful's own stated "7 signs" (unresponsive support,
  no visibility, custom dev required per connection).
- **Common objections**: Migration risk — ripping out a working (if painful)
  system is scary regardless of how bad it is; sunk cost in the current
  provider's custom mappings; needing to prove ROI/uptime before championing
  a switch internally.
- **Channel/format preference**: Technical content — API docs, the EDI
  glossary, the real-time validator tool — self-serve research before any
  sales conversation, consistent with Orderful's own site structure.

### Owner/executive buyer at a smaller logistics, carrier, or 3PL company

- **Title(s)**: President, Owner, President of Integrated Logistics
  (evidenced by NFI's and Heartland Logistics Group's case studies).
- **Which company segment they map to**: Smaller logistics, carrier, and 3PL
  companies where EDI is closer to revenue infrastructure than IT overhead —
  the company literally can't onboard a new shipper/broker relationship
  without it.
- **What they care about / priorities**: Revenue directly, not IT hygiene —
  "if we're not moving loads, we're not making money" (KBX's own quoted
  language). Growing client base without growing headcount — Heartland
  Logistics' own cited outcome was "Zero Additional Headcount" alongside
  100% growth in client base.
- **Messaging angle that resonates**: EDI as a growth lever, not a back-office
  cost center — framed around revenue/client-count impact and speed to
  onboard a new client relationship, not technical features.
- **Common objections**: Budget sensitivity at this company size; reluctance
  to add another vendor relationship to manage personally, since this buyer
  is often also the one managing most vendor relationships directly.
- **Channel/format preference**: Numbers-first case studies (days-to-onboard,
  headcount-avoided, client-base growth) over technical detail — matches
  exactly how Orderful's own site presents these customers.

## Open gaps

All three personas are inferred from a small set of public case-study titles
(five companies total), not from customer interviews, deal notes, or sales
team input — the real confirmation step. Specifically unconfirmed:
- Whether these three are the actual segments Orderful's sales team targets,
  or just the ones with the best-looking public case studies.
- Real objection patterns and what actually overcomes them in a live deal.
- Whether a fourth persona exists for the "SaaS & Tech Platforms" vertical
  (an engineering/product buyer embedding EDI via API) — the site lists this
  vertical but no case study with a named buyer title was found to build a
  persona from.
