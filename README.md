# Antimetal

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

Antimetal is a New York based software company building an autonomous production-management platform for engineering teams — "everything that happens after you deploy". It maintains a continuously updated world model of a customer's production stack and runs specialized AI agents that patrol for risk and drift, triage noisy signals into structured issues, investigate incidents down to a root cause, and generate production-ready fixes tied back to the underlying evidence. It connects to more than ninety cloud, observability, CI/CD, incident and code tools — AWS, Google Cloud, Azure, Kubernetes, Datadog, Grafana, Prometheus, Sentry, Splunk, New Relic, Honeycomb, PagerDuty, incident.io, GitHub, Vercel and Slack among them. Antimetal publishes a public REST API (the Antimetal External API, at bff.antimetal.com/api/v2) covering issues, investigation results, evidential artifacts and a natural-language query endpoint, a remote MCP server at mcp.antimetal.com with OAuth 2.1 and API-key auth, an official TypeScript SDK, published Agent Skills for Claude Code and Cursor, open protobuf definitions for its infrastructure agent, and a Terraform provider and Helm charts.

**Areas:** Company · Observability · Incident Management · Site Reliability Engineering · Artificial Intelligence · Agents · DevOps · Cloud Infrastructure · Kubernetes · Root Cause Analysis · MCP · A2A

## Antimetal on APIs.io

Everything profiled for Antimetal is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/antimetal/](https://apis.io/providers/antimetal/)** — or go straight to one of the APIs or properties below.

### APIs (5)

- [Antimetal MCP Server](https://apis.io/apis/antimetal/antimetal-mcp-server/) — Remote Model Context Protocol server exposing Antimetal's investigation, root-cause analysis and remediation capabilities to MCP-compatible clients such as…
- [Antimetal Agent APIs (Protobuf)](https://apis.io/apis/antimetal/antimetal-agent-apis/) — Public protobuf/Connect definitions for the Antimetal system agent — the component that connects customer infrastructure to the Antimetal platform. Covers…
- [Antimetal Artifacts API](https://apis.io/apis/antimetal/antimetal-artifacts-api/) — The Artifacts API from Antimetal — 1 operation(s) for artifacts.
- [Antimetal Issues API](https://apis.io/apis/antimetal/antimetal-issues-api/) — The Issues API from Antimetal — 4 operation(s) for issues.
- [Antimetal Query API](https://apis.io/apis/antimetal/antimetal-query-api/) — The Query API from Antimetal — 1 operation(s) for query.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [antimetal](https://apis.io/servers/antimetal/antimetal/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Antimetal Agentic Access](https://apis.io/agentic-access/antimetal/antimetal-agentic-access/)

#### Collections (3)

Postman and Open Collection request collections.

- [Antimetal External Artifacts API](https://apis.io/collections/antimetal/open-antimetal-artifacts-api/)
- [Antimetal External Issues API](https://apis.io/collections/antimetal/open-antimetal-issues-api/)
- [Antimetal External Query API](https://apis.io/collections/antimetal/open-antimetal-query-api/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Antimetal External Api Overlay](https://apis.io/overlays/antimetal/antimetal-external-api-overlay/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Antimetal Authentication](https://apis.io/security/antimetal/antimetal-authentication/)
- [Antimetal Domain Security](https://apis.io/security/antimetal/antimetal-domain-security/)
- [Antimetal Trust Center](https://apis.io/security/antimetal/antimetal-trust-center/)
- [Antimetal Vulnerability Disclosure](https://apis.io/security/antimetal/antimetal-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Antimetal Scopes](https://apis.io/scopes/antimetal/antimetal-scopes/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.antimetal.com/)
- [Documentation](https://docs.antimetal.com/)
- [Getting started](https://docs.antimetal.com/quick-start)
- [API reference](https://docs.antimetal.com/api-reference/issues/fetch-issues-for-an-organization)
- [Sign up](https://overlook.antimetal.com/)
- [Blog](https://antimetal.com/blog)
- [Security](https://docs.antimetal.com/admin/security)
- [Compliance](https://docs.antimetal.com/admin/security)
- [Terms of service](https://antimetal.com/terms)
- [Privacy policy](https://antimetal.com/privacy)
- [GitHub](https://github.com/antimetal)
- [Status](https://status.antimetal.com/)

## API Evangelist rating

**Kin Score 52.5** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 75.0 |
| Contract quality | 52.4 |
| Contract governance | 18.2 |
| Operational transparency | 36.8 |
| Developer ergonomics | 71.4 |
| Access clarity | 36.8 |

**Agent readiness 55.1** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | verified |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | — |
| Rate Limit Signal | — |
| Event Surface Described | — |
| Agent Skills | yes |
| Well Known Catalog | yes |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | verified |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |
| Pagination Ratio | partial |
| Operation Distinctiveness | distinct |

**Regulatory alignment 41.8** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/antimetal/](https://apis.io/providers/antimetal/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Antimetal: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/antimetal/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
