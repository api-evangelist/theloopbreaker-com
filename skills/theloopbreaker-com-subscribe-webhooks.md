---
generated: '2026-09-19'
method: generated
name: Subscribe to Vaultfire events with a webhook
description: Register an HTTPS webhook for bond, reputation, credential, dispute, bridge, insurance, vouch and task events, list what is registered, and remove it.
api: openapi/theloopbreaker-com-openapi.yml
operations: [listWebhooks, registerWebhook, deleteWebhook]
source: >-
  Grounded in openapi/theloopbreaker-com-openapi.yml (operationIds and the 16-value events enum verified
  verbatim) and steps 17-18 of https://theloopbreaker.com/llms.txt. The 503 observation is from a live
  2026-09-19 POST to /api/agent/webhooks.
---

# Subscribe to Vaultfire events with a webhook

The event catalog is in `asyncapi/theloopbreaker-com-webhooks.yml`.

## Steps
1. **See the valid events** — `listWebhooks` (`GET /agent/webhooks`) with no `address` returns the event catalog; with `?address=0x...` it lists that agent's registrations.
2. **Register** — `registerWebhook` (`POST /agent/webhooks`) with `{"address": "0x...", "url": "https://your-agent.example/webhook", "events": ["bond.created", "reputation.updated"], "chain": "base"}` (`address`, `url`, `events` required; `chain` defaults to `all`). Valid `events` values: bond.created, bond.activated, bond.completed, reputation.updated, credential.issued, credential.revoked, dispute.filed, dispute.resolved, bridge.synced, insurance.claim_filed, insurance.payout, agent.registered, vouch.received, vouch.slashed, task.assigned, task.completed. A 201 returns the webhook ID (`wh_...`) and a signing secret — store the secret; it is how you verify deliveries.
3. **Remove** — `deleteWebhook` (`DELETE /agent/webhooks?id=wh_...`) (`id` required). This is the only reversal path on the API; no window is stated.

## Rules
- On 2026-09-19 the live endpoint answered `503 {"error":"webhook write service is not configured","code":"webhook_auth_unconfigured"}` to a registration attempt. Treat 503 with that `code` as "the feature is not switched on", not as a transient outage, and do not retry in a tight loop.
- The signature scheme for deliveries (header name, algorithm) is not documented anywhere probed; the only published fact is that a signing secret is returned at registration.
