# Vaultfire Protocol

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Vaultfire Protocol (theloopbreaker.com) is on-chain trust infrastructure for AI agents — "KYA, Know Your Agent". It runs 134 smart contracts across Base, Avalanche, Arbitrum and Polygon for ERC-8004 agent identity, verifiable reputation (Street Cred), partnership and accountability bonds, a USDC task-escrow marketplace, VNS agent names, key delegation (VKP), ZK trust attestations and a cross-chain trust bridge. Its public Agent Hub API exposes 34 free REST operations (OpenAPI 3.1) that read those contracts and return unsigned transactions for the caller to sign, plus 77 x402-priced endpoints paid per call in USDC, an 18-skill A2A agent card, llms.txt, agents.txt, a published Agent Skill and a stdio MCP server on npm.

**Areas:** AI Agents · Agent Identity · Trust · Reputation · Blockchain · Web3 · Payments · x402 · MCP · A2A · Company

## Vaultfire Protocol on APIs.io

Everything profiled for Vaultfire Protocol is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/theloopbreaker-com/](https://apis.io/providers/theloopbreaker-com/)** — or go straight to one of the APIs or properties below.

### APIs (18)

- [Vaultfire Trust Service (x402)](https://apis.io/apis/theloopbreaker-com/vaultfire-trust-service-x402/) — The priced projection of the same trust surface: 77 endpoints under /api/x402/* (29 priced GET reads, 46 priced POST transaction-preparation actions, 2…
- [Vaultfire Protocol Agent API](https://apis.io/apis/theloopbreaker-com/theloopbreaker-com-agent-api/) — Agent identity and trust profiles
- [Vaultfire Protocol Analytics API](https://apis.io/apis/theloopbreaker-com/theloopbreaker-com-analytics-api/) — Agent performance analytics
- [Vaultfire Protocol Bonds API](https://apis.io/apis/theloopbreaker-com/theloopbreaker-com-bonds-api/) — Partnership and accountability bonds
- [Vaultfire Protocol Bridge API](https://apis.io/apis/theloopbreaker-com/theloopbreaker-com-bridge-api/) — Cross-chain trust sync
- [Vaultfire Protocol Compliance API](https://apis.io/apis/theloopbreaker-com/theloopbreaker-com-compliance-api/) — Mission enforcement, privacy, validation
- [Vaultfire Protocol Discovery API](https://apis.io/apis/theloopbreaker-com/theloopbreaker-com-discovery-api/) — Agent directory and search
- [Vaultfire Protocol Disputes API](https://apis.io/apis/theloopbreaker-com/theloopbreaker-com-disputes-api/) — Dispute resolution
- [Vaultfire Protocol Governance API](https://apis.io/apis/theloopbreaker-com/theloopbreaker-com-governance-api/) — Multisig governance
- [Vaultfire Protocol Identity API](https://apis.io/apis/theloopbreaker-com/theloopbreaker-com-identity-api/) — VNS naming service
- [Vaultfire Protocol Insurance API](https://apis.io/apis/theloopbreaker-com/theloopbreaker-com-insurance-api/) — Bond insurance pool
- [Vaultfire Protocol Keys API](https://apis.io/apis/theloopbreaker-com/theloopbreaker-com-keys-api/) — Vaultfire Key Protocol — session keys, delegation, wallets
- [Vaultfire Protocol Protocol API](https://apis.io/apis/theloopbreaker-com/theloopbreaker-com-protocol-api/) — Protocol-wide stats and contracts
- [Vaultfire Protocol Routing API](https://apis.io/apis/theloopbreaker-com/theloopbreaker-com-routing-api/) — Task routing and matching
- [Vaultfire Protocol System API](https://apis.io/apis/theloopbreaker-com/theloopbreaker-com-system-api/) — Health and system status
- [Vaultfire Protocol Tasks API](https://apis.io/apis/theloopbreaker-com/theloopbreaker-com-tasks-api/) — Task marketplace with USDC escrow
- [Vaultfire Protocol Trust API](https://apis.io/apis/theloopbreaker-com/theloopbreaker-com-trust-api/) — Reputation, vouching, credentials, oracles
- [Vaultfire Protocol Webhooks API](https://apis.io/apis/theloopbreaker-com/theloopbreaker-com-webhooks-api/) — Event subscriptions

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Theloopbreaker Com Webhooks](https://apis.io/asyncapis/theloopbreaker-com/theloopbreaker-com-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [vaultfire](https://apis.io/servers/theloopbreaker-com/vaultfire/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Theloopbreaker Com Openapi Overlay](https://apis.io/overlays/theloopbreaker-com/theloopbreaker-com-openapi-overlay/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Theloopbreaker Com Authentication](https://apis.io/security/theloopbreaker-com/theloopbreaker-com-authentication/)
- [Theloopbreaker Com Domain Security](https://apis.io/security/theloopbreaker-com/theloopbreaker-com-domain-security/)
- [Theloopbreaker Com Vulnerability Disclosure](https://apis.io/security/theloopbreaker-com/theloopbreaker-com-vulnerability-disclosure/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Theloopbreaker Com Plans Pricing](https://apis.io/plans/theloopbreaker-com/theloopbreaker-com-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Theloopbreaker Com Rate Limits](https://apis.io/rate-limits/theloopbreaker-com/theloopbreaker-com-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://theloopbreaker.com/)
- [Documentation](https://theloopbreaker.com/architecture)
- [Getting started](https://theloopbreaker.com/start)
- [Pricing](https://theloopbreaker.com/.well-known/x402.json)
- [Support](https://theloopbreaker.com/partners)
- [Security](https://theloopbreaker.com/security)
- [Terms of service](https://theloopbreaker.com/terms)
- [Privacy policy](https://theloopbreaker.com/privacy)

## API Evangelist rating

**Kin Score 53.0** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 71.7 |
| Contract quality | 49.2 |
| Contract governance | 18.2 |
| Operational transparency | 60.5 |
| Developer ergonomics | 59.5 |
| Access clarity | 52.6 |

**Agent readiness 41.0** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | documented (partial credit) |
| MCP Server | documented (partial credit) |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | yes |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | conformant |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | distinct |

**Regulatory alignment 31.3** — Payments

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/theloopbreaker-com/](https://apis.io/providers/theloopbreaker-com/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Vaultfire Protocol: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/theloopbreaker-com/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
