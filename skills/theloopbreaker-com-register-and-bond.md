---
generated: '2026-09-19'
method: generated
name: Register an agent and pledge a partnership bond
description: Prepare the ERC-8004 registration and partnership-bond transactions through the Vaultfire API, sign them with the caller's own wallet, then verify the result.
api: openapi/theloopbreaker-com-openapi.yml
operations: [registerAgent, createBond, getAgentStatus, getPartnerships, getContracts]
source: >-
  Grounded in openapi/theloopbreaker-com-openapi.yml (operationIds and requestBody fields verified verbatim)
  and steps 2 and 3 of https://theloopbreaker.com/llms.txt; the irreversibility rule is from
  https://theloopbreaker.com/terms section 3 and the @vaultfire/mcp-server README.
---

# Register an agent and pledge a partnership bond

Vaultfire's write endpoints do not execute anything. They return an **unsigned transaction**; the caller signs and broadcasts it from a self-custodied wallet. There is no API key. See `conventions/theloopbreaker-com-conventions.yml` (reversibility) before you start: once broadcast, an on-chain transaction cannot be reversed, refunded or modified by Vaultfire.

## Steps
1. **Check you are not already registered** — `getAgentStatus` (`GET /agent/status?address=0x...`). If `registered` is true, skip to step 3.
2. **Build the registration transaction** — `registerAgent` (`POST /agent/register`) with `{"name": "...", "walletAddress": "0x...", "chain": "base"}` (`name` and `walletAddress` required). The 200 body is an unsigned transaction targeting the chain's ERC8004IdentityRegistry. Sign and broadcast it with the wallet that owns `walletAddress`.
3. **Build the bond transaction** — `createBond` (`POST /agent/bond`) with `{"walletAddress": "0x...", "agentAddress": "0x...", "amountEth": "0.01", "chain": "base"}` (all three required). llms.txt states the minimum is 0.01 ETH (Bronze tier); tiers are Bronze 0.01 / Silver 0.05 / Gold 0.1 / Platinum 0.5 ETH. Sign and broadcast.
4. **Verify** — `getPartnerships` (`GET /agent/partnerships?address=0x...`) should list the new bond; `getAgentStatus` should now show `hasBond: true` and a higher `trustScore`.
5. **If you need contract addresses or ABIs directly** — `getContracts` (`GET /contracts`) returns every address across all four chains; it is the source SKILL.md calls the "canonical truth source".

## Rules
- Do not send `PRIVATE_KEY` or a seed phrase to any Vaultfire endpoint; the API never asks for one. Keys are only used locally, by your own signer (or by the stdio MCP server's write tools, which is a different surface).
- `chain` must be one of `base | avalanche | arbitrum | polygon`.
- Human-facing partnership bonds and company-facing accountability bonds are different products; this skill covers partnership bonds only (`createBond`).
