# workflows/

Orchestration for this client instance: what triggers what, in what order (signal
detected -> score -> draft; inbound event -> identity check -> qualify -> route).
Empty in the template — the actual trigger/orchestration tooling (n8n or otherwise)
is a "how" decision made per client, not specified generically here.
