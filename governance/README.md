# governance/

The discipline that holds regardless of how automated a given client instance gets:

- Never fabricate data — a missing fact is reported as missing, never guessed at
  and presented as real (applies to onboarding inventories, signal research, and
  enrichment lookups alike).
- What the agent may do on its own today for this client vs. what needs a human —
  see `business.yaml`'s `autonomy` block. Starts at draft-only for both directions;
  graduates per client based on real, manually-reviewed accuracy over time (see
  `../docs/eval/eval-loop.md`) — not a fixed schedule.
- Suppression / do-not-contact rules for this client, once they exist.

Empty of client-specific rules in the template — this file describes the standing
principles; a real instance adds its own suppression list and any client-specific
exceptions alongside them.

## What would go here for Orderful

A real suppression/do-not-contact list, once real prospecting starts —
Orderful's own existing customers first (so outbound never re-pitches an
account that's already a customer, a check `../skills/account-research-skill.md`'s
prior-relationship step depends on having), plus anyone who's explicitly
opted out. Possibly a client-specific exception to the standing draft-only
rule once autonomy actually graduates — `../GOING_LIVE.md` item 5 flags that
sign-off as needed but doesn't resolve it, since it's Orderful's call, not
something to default into here. Not built because there's no real customer
list or governance sign-off yet.
