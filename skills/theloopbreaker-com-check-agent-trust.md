---
generated: '2026-09-19'
method: generated
name: Check an agent's trust profile before you rely on it
description: Look up an agent's ERC-8004 identity, bond posture and Street Cred score on Vaultfire, in bulk if needed, and confirm the platform is healthy first.
api: openapi/theloopbreaker-com-openapi.yml
operations: [getHealth, getAgentStatus, batchAgentStatus, getAgentAnalytics, getPartnerships]
source: >-
  Grounded in openapi/theloopbreaker-com-openapi.yml (operationIds verified verbatim) and the "How to interact
  with this site as an agent" steps 1, 16, 19 and 20 of https://theloopbreaker.com/llms.txt. Response field
  names come from a live 2026-09-19 call to getAgentStatus.
---

# Check an agent's trust profile

All operations here are public GETs (and one POST) on `https://theloopbreaker.com/api`. No key, no wallet, no signature. See `authentication/theloopbreaker-com-authentication.yml`.

## Steps
1. **Confirm the platform is up** — `getHealth` (`GET /health`). Expect `status: healthy` and one `ok` entry per chain in `chains[]` (base, avalanche, arbitrum, polygon). llms.txt says to call this "before committing to using the platform".
2. **Look up one agent** — `getAgentStatus` (`GET /agent/status?address=0x...`). The `address` query parameter is required; omitting it returns `400 {"error":"Missing required query param: address"}`. Read `registered`, `hasBond`, `bondActive`, `bondAmountEth`, `trustScore` (Street Cred, 0-95) and `vnsName`.
3. **Or look up many at once** — `batchAgentStatus` (`POST /agent/status/batch`) with `{"addresses": [...], "chain": "base"}`; at most 25 addresses per call (`maxItems: 25`). Prefer this over looping step 2.
4. **Go deeper when the score matters** — `getAgentAnalytics` (`GET /agent/analytics?address=0x...&chain=base`) for the composite view (tier, bonds, staking, attestations, credentials, disputes, bridge recognition), and `getPartnerships` (`GET /agent/partnerships?address=0x...`) for the individual bonds.

## Rules
- `chain` accepts `base | avalanche | arbitrum | polygon`; Base is the hub chain and the default.
- Rate limit is documented as 120 requests/minute with `X-RateLimit-*` headers and `Retry-After` on 429 — but the headers were not present on live responses when this skill was written; back off on a 429 status regardless. See `rate-limits/theloopbreaker-com-rate-limits.yml`.
- Errors are a flat `{"error": "..."}` object, not RFC 9457. See `errors/theloopbreaker-com-problem-types.yml`.
- Registration is permissionless and is not by itself a trust signal (SKILL.md, "What You Probably Got Wrong"); weigh `bondActive` and `trustScore`, not `registered`.
