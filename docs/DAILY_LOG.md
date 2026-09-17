# Daily log

Newest first. See `DAILY_LOG_PROCESS.md` for the practice this follows.

## 2026-09-17

**What happened**: Scaffolded this instance from the `gtm-bd-operator`
template as a demo applied to Orderful, to show their CRO (Mike Head) a
system I built — not a pitch to run BD for Orderful, not a live client
engagement. Built
out, from public research only (orderful.com, their blog and case studies,
retailer EDI-compliance research, competitor reviews, retail trade press):
`onboarding/company-understanding-inventory.md`, `icp-template.md`,
`persona-template.md`, and `signal-inventory-template.md`; then downstream
concept docs — `score/scoring-model.md`, `score/eval-example.md`,
`templates/account-research-brief.md`, `templates/outreach-templates.md`,
and `templates/outreach-sequence.md` (with multi-threading); then one real
worked example threading a real company (True Classic — not an Orderful
customer) through the entire chain at
`output/example-brief-true-classic.md`. Wrote `HOW_THIS_WORKS.md` as a
plain-language explainer for Mike Head specifically, including an AI-vs-human
responsibility breakdown and what this needs from Orderful to become real.
Did a full review pass afterward and fixed several real errors: a broken
signal-numbering sequence (jumped from #2 to #4 with no #3, after an earlier
edit), two places that had propagated the resulting wrong numbers downstream
(`outreach-templates.md`, `score/eval-example.md`), a false citation in
`persona-template.md` (claimed `icp-template.md` specified a "~200 employees"
threshold it never actually states), an internal contradiction in
`score/scoring-model.md` between its own Combined-tier table and the True
Classic example it was supposed to support (a single Tier 1 signal scored
"Med" per the table's original threshold but was treated as "High" — i.e.
Hot — everywhere else), a markdown header broken across a hard line wrap in
`outreach-sequence.md`, and this file itself, which had been copied over
verbatim from the template and was still describing the *template's* own
history (Stack Industrial, an unrelated IT/antivirus issue) rather than
anything about Orderful.

**Decisions made**:
- Repo stays private for now; visibility/sharing decision (flip public vs.
  invite Mike Head as a collaborator) deferred to John.
- Governance discipline carried through every layer, not just onboarding:
  every file states its own status (concept vs. verified) and open gaps: no
  fabricated contact names, no invented outcome data presented as real.
- Checked Target's actual terms of use before designing the compliance-signal
  verification step — found they explicitly bar an agent (not a human) from
  accessing/querying the site under any circumstances, so that check routes
  through the candidate company's own public materials instead, not the
  retailer's site.
- `tech-stack-audit-template.md` and `storage-decision-worksheet.md` left
  intentionally blank — out of scope for a public-research-only pass.

**Still open / next**:
- No client engagement with Orderful, and none being pursued — this is a
  capability demo, not a BD pitch.
- Repo visibility/sharing decision with Mike Head still pending.
- Everything in this instance is unverified against Orderful's real data —
  see each file's own "Open gaps" section and `HOW_THIS_WORKS.md`'s "What
  this needs from Orderful to go from demo to real."
