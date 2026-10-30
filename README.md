# LaunchDarkly

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

LaunchDarkly is a feature management and runtime control platform. Development teams use it to wrap releases in feature flags, target variations at specific users, contexts, segments and environments, run experiments and guarded rollouts, and turn a change back off without shipping new code. The platform now extends the same targeting, approval and audit machinery to AI through AgentControl, where prompts, models, tools and agent graphs are versioned and rolled out as configs, and to observability through session replay, errors, logs and traces. LaunchDarkly publishes a 401-operation REST API, more than thirty SDKs across thirteen client-side, thirteen server-side and four edge runtimes, a self-hosted Relay Proxy, a CLI, and a hosted MCP server exposing 125 tools to AI clients. LaunchDarkly is operated by Catamorphic Co.

**Areas:** Feature Flags · Feature Management · Experimentation · Observability · Continuous Delivery · DevOps · AI Agents · Release Management · Developer Tools · T1

## LaunchDarkly on APIs.io

Everything profiled for LaunchDarkly is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/launchdarkly/](https://apis.io/providers/launchdarkly/)** — or go straight to one of the APIs or properties below.

### APIs (30)

- [LaunchDarkly Webhooks API](https://apis.io/apis/launchdarkly/webhooks-api/) — The LaunchDarkly Webhooks API allows developers to build custom integrations that subscribe to activity events within LaunchDarkly. When actions occur such…
- [launchdarkly Access Tokens API](https://apis.io/apis/launchdarkly/launchdarkly-access-tokens-api/) — Create and manage personal and service access tokens used to authenticate API requests.
- [launchdarkly Account Members API](https://apis.io/apis/launchdarkly/launchdarkly-account-members-api/) — Manage team members, invitations, and member roles within a LaunchDarkly account.
- [launchdarkly Approvals API](https://apis.io/apis/launchdarkly/launchdarkly-approvals-api/) — Manage approval requests and workflows for flag changes that require review before deployment.
- [launchdarkly Audit Log API](https://apis.io/apis/launchdarkly/launchdarkly-audit-log-api/) — Access the change history of all modifications made to resources in the LaunchDarkly account.
- [launchdarkly Client-Side Evaluation API](https://apis.io/apis/launchdarkly/launchdarkly-client-side-evaluation-api/) — Flag evaluation endpoints for client-side and mobile SDKs using environment IDs or mobile keys for authentication.
- [launchdarkly Client-Side Streaming API](https://apis.io/apis/launchdarkly/launchdarkly-client-side-streaming-api/) — Server-Sent Events streaming endpoints for client-side and mobile SDKs to receive real-time flag updates.
- [launchdarkly Code References API](https://apis.io/apis/launchdarkly/launchdarkly-code-references-api/) — View code references that show where feature flags are used in your codebase.
- [launchdarkly Custom Roles API](https://apis.io/apis/launchdarkly/launchdarkly-custom-roles-api/) — Define custom roles with fine-grained permissions using resource specifiers and actions.
- [launchdarkly Environments API](https://apis.io/apis/launchdarkly/launchdarkly-environments-api/) — Manage environments within projects such as production, staging, and development.
- [launchdarkly Experiments API](https://apis.io/apis/launchdarkly/launchdarkly-experiments-api/) — Create and manage experiments to measure the impact of feature flag variations on metrics.
- [launchdarkly Feature Flags API](https://apis.io/apis/launchdarkly/launchdarkly-feature-flags-api/) — Create, update, and manage feature flags and their targeting rules across projects and environments.
- [launchdarkly Flag Triggers API](https://apis.io/apis/launchdarkly/launchdarkly-flag-triggers-api/) — Create triggers that allow external services to toggle feature flags via unique webhook URLs.
- [launchdarkly Integration Audit Log Subscriptions API](https://apis.io/apis/launchdarkly/launchdarkly-integration-audit-log-subscriptions-api/) — Manage integrations that subscribe to audit log events and forward them to external tools.
- [launchdarkly Metrics API](https://apis.io/apis/launchdarkly/launchdarkly-metrics-api/) — Define and manage metrics used to measure experiment outcomes and feature flag impact.
- [launchdarkly PHP Polling API](https://apis.io/apis/launchdarkly/launchdarkly-php-polling-api/) — Polling endpoints for PHP server-side SDKs which do not support streaming mode.
- [launchdarkly Projects API](https://apis.io/apis/launchdarkly/launchdarkly-projects-api/) — Manage projects that organize feature flags and other resources.
- [launchdarkly Relay Proxy Configurations API](https://apis.io/apis/launchdarkly/launchdarkly-relay-proxy-configurations-api/) — Manage automatic configuration entries for LaunchDarkly Relay Proxy instances.
- [launchdarkly Releases API](https://apis.io/apis/launchdarkly/launchdarkly-releases-api/) — Manage release pipelines for coordinating feature flag rollouts across environments.
- [launchdarkly Segments API](https://apis.io/apis/launchdarkly/launchdarkly-segments-api/) — Create and manage user segments for targeting groups of contexts with feature flags.
- [launchdarkly Server-Side Evaluation API](https://apis.io/apis/launchdarkly/launchdarkly-server-side-evaluation-api/) — Flag evaluation endpoints for server-side SDKs using SDK keys for authentication.
- [launchdarkly Server-Side Streaming API](https://apis.io/apis/launchdarkly/launchdarkly-server-side-streaming-api/) — Server-Sent Events streaming endpoints for server-side SDKs to receive real-time flag updates.
- [launchdarkly Status API](https://apis.io/apis/launchdarkly/launchdarkly-status-api/) — Health and status monitoring endpoints for the Relay Proxy. No authentication is required for these endpoints.
- [launchdarkly Tags API](https://apis.io/apis/launchdarkly/launchdarkly-tags-api/) — The Tags API from launchdarkly — 1 operation(s) for tags.
- [launchdarkly Teams API](https://apis.io/apis/launchdarkly/launchdarkly-teams-api/) — Organize account members into teams for collaborative flag management and permissions.
- [launchdarkly Webhooks API](https://apis.io/apis/launchdarkly/launchdarkly-webhooks-api/) — Configure webhooks to receive HTTP POST notifications when changes occur in LaunchDarkly.
- [launchdarkly Workflows API](https://apis.io/apis/launchdarkly/launchdarkly-workflows-api/) — Create and manage automated workflows for scheduling and orchestrating flag changes.
- [LaunchDarkly MCP Server](https://apis.io/apis/launchdarkly/launchdarkly-mcp-server/) — LaunchDarkly operates a first-party hosted Model Context Protocol server at https://mcp.launchdarkly.com/mcp/launchdarkly, reachable by any MCP client over…
- [LaunchDarkly Backup API](https://apis.io/apis/launchdarkly/launchdarkly-backup-api/) — The Backup API from LaunchDarkly — 1 operation(s) for backup.
- [LaunchDarkly Debug Sessions API](https://apis.io/apis/launchdarkly/launchdarkly-debug-sessions-api/) — The Debug Sessions API from LaunchDarkly — 3 operation(s) for debug sessions.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [LaunchDarkly Webhooks Events](https://apis.io/asyncapis/launchdarkly/launchdarkly-webhooks-asyncapi/)

#### Event channels (1)

Individual events and webhooks the provider emits.

- [/webhook](https://apis.io/channels/launchdarkly/webhook/)

#### GraphQL (1)

GraphQL schemas.

- [Moved to /providers/launchdarkly/](https://apis.io/graphqls/launchdarkly/launchdarkly-graphql/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [LaunchDarkly MCP Server](https://apis.io/servers/launchdarkly/launchdarkly-mcp-server/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Launchdarkly Agentic Access](https://apis.io/agentic-access/launchdarkly/launchdarkly-agentic-access/)

#### JSON Schema (70)

The data models the API reads and writes.

- [AccessToken](https://apis.io/schemas/launchdarkly/launchdarkly-accesstoken/)
- [AccessTokenBody](https://apis.io/schemas/launchdarkly/launchdarkly-accesstokenbody/)
- [AccessTokens](https://apis.io/schemas/launchdarkly/launchdarkly-accesstokens/)
- [ApprovalRequest](https://apis.io/schemas/launchdarkly/launchdarkly-approvalrequest/)
- [ApprovalRequestBody](https://apis.io/schemas/launchdarkly/launchdarkly-approvalrequestbody/)
- [ApprovalRequests](https://apis.io/schemas/launchdarkly/launchdarkly-approvalrequests/)
- [AuditLogEntries](https://apis.io/schemas/launchdarkly/launchdarkly-auditlogentries/)
- [AuditLogEntry](https://apis.io/schemas/launchdarkly/launchdarkly-auditlogentry/)
- [Clause](https://apis.io/schemas/launchdarkly/launchdarkly-clause/)
- [CodeReferenceRepositories](https://apis.io/schemas/launchdarkly/launchdarkly-codereferencerepositories/)
- [CustomRole](https://apis.io/schemas/launchdarkly/launchdarkly-customrole/)
- [CustomRoleBody](https://apis.io/schemas/launchdarkly/launchdarkly-customrolebody/)
- [CustomRoles](https://apis.io/schemas/launchdarkly/launchdarkly-customroles/)
- [Environment](https://apis.io/schemas/launchdarkly/launchdarkly-environment/)
- [EnvironmentBody](https://apis.io/schemas/launchdarkly/launchdarkly-environmentbody/)
- [Environments](https://apis.io/schemas/launchdarkly/launchdarkly-environments/)
- [EnvironmentStatus](https://apis.io/schemas/launchdarkly/launchdarkly-environmentstatus/)
- [EvaluationContext](https://apis.io/schemas/launchdarkly/launchdarkly-evaluationcontext/)
- [Experiment](https://apis.io/schemas/launchdarkly/launchdarkly-experiment/)
- [ExperimentBody](https://apis.io/schemas/launchdarkly/launchdarkly-experimentbody/)
- [Experiments](https://apis.io/schemas/launchdarkly/launchdarkly-experiments/)
- [LaunchDarkly Feature Flag](https://apis.io/schemas/launchdarkly/launchdarkly-feature-flag/)
- [FeatureFlag](https://apis.io/schemas/launchdarkly/launchdarkly-featureflag/)
- [FeatureFlagBody](https://apis.io/schemas/launchdarkly/launchdarkly-featureflagbody/)
- [FeatureFlags](https://apis.io/schemas/launchdarkly/launchdarkly-featureflags/)
- …and 45 more published on APIs.io

#### JSON Structure (1)

Data models expressed in JSON Structure.

- [Launchdarkly Structure](https://apis.io/json-structure/launchdarkly/launchdarkly-structure/)

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Launchdarkly Context](https://apis.io/jsonld/launchdarkly/launchdarkly-context/)

#### Vocabulary (1)

The provider's domain terms, defined.

- [Launchdarkly Domain Vocabulary](https://apis.io/vocabularies/launchdarkly/launchdarkly-vocabulary/)

#### Collections (28)

Postman and Open Collection request collections.

- [LaunchDarkly Relay Proxy Access Tokens API](https://apis.io/collections/launchdarkly/open-launchdarkly-access-tokens-api/)
- [LaunchDarkly Relay Proxy Access Tokens Account Members API](https://apis.io/collections/launchdarkly/open-launchdarkly-account-members-api/)
- [LaunchDarkly Relay Proxy Access Tokens Approvals API](https://apis.io/collections/launchdarkly/open-launchdarkly-approvals-api/)
- [LaunchDarkly Relay Proxy Access Tokens Audit Log API](https://apis.io/collections/launchdarkly/open-launchdarkly-audit-log-api/)
- [LaunchDarkly Relay Proxy Access Tokens Client-Side Evaluation API](https://apis.io/collections/launchdarkly/open-launchdarkly-client-side-evaluation-api/)
- [LaunchDarkly Relay Proxy Access Tokens Client-Side Streaming API](https://apis.io/collections/launchdarkly/open-launchdarkly-client-side-streaming-api/)
- [LaunchDarkly Relay Proxy Access Tokens Code References API](https://apis.io/collections/launchdarkly/open-launchdarkly-code-references-api/)
- [LaunchDarkly Relay Proxy Access Tokens Custom Roles API](https://apis.io/collections/launchdarkly/open-launchdarkly-custom-roles-api/)
- [LaunchDarkly Relay Proxy Access Tokens Environments API](https://apis.io/collections/launchdarkly/open-launchdarkly-environments-api/)
- [LaunchDarkly Relay Proxy Access Tokens Experiments API](https://apis.io/collections/launchdarkly/open-launchdarkly-experiments-api/)
- [LaunchDarkly Relay Proxy Access Tokens Feature Flags API](https://apis.io/collections/launchdarkly/open-launchdarkly-feature-flags-api/)
- [LaunchDarkly Relay Proxy Access Tokens Flag Triggers API](https://apis.io/collections/launchdarkly/open-launchdarkly-flag-triggers-api/)
- [LaunchDarkly Relay Proxy Access Tokens Integration Audit Log Subscriptions API](https://apis.io/collections/launchdarkly/open-launchdarkly-integration-audit-log-subscriptions-api/)
- [LaunchDarkly Relay Proxy Access Tokens Metrics API](https://apis.io/collections/launchdarkly/open-launchdarkly-metrics-api/)
- [LaunchDarkly Relay Proxy Access Tokens PHP Polling API](https://apis.io/collections/launchdarkly/open-launchdarkly-php-polling-api/)
- [LaunchDarkly Relay Proxy Access Tokens Projects API](https://apis.io/collections/launchdarkly/open-launchdarkly-projects-api/)
- [LaunchDarkly Relay Proxy](https://apis.io/collections/launchdarkly/open-launchdarkly-relay-proxy/)
- [LaunchDarkly Relay Proxy Access Tokens Relay Proxy Configurations API](https://apis.io/collections/launchdarkly/open-launchdarkly-relay-proxy-configurations-api/)
- [LaunchDarkly Relay Proxy Access Tokens Releases API](https://apis.io/collections/launchdarkly/open-launchdarkly-releases-api/)
- [LaunchDarkly REST API](https://apis.io/collections/launchdarkly/open-launchdarkly-rest-api/)
- [LaunchDarkly Relay Proxy Access Tokens Segments API](https://apis.io/collections/launchdarkly/open-launchdarkly-segments-api/)
- [LaunchDarkly Relay Proxy Access Tokens Server-Side Evaluation API](https://apis.io/collections/launchdarkly/open-launchdarkly-server-side-evaluation-api/)
- [LaunchDarkly Relay Proxy Access Tokens Server-Side Streaming API](https://apis.io/collections/launchdarkly/open-launchdarkly-server-side-streaming-api/)
- [LaunchDarkly Relay Proxy Access Tokens Status API](https://apis.io/collections/launchdarkly/open-launchdarkly-status-api/)
- [LaunchDarkly Relay Proxy Access Tokens Tags API](https://apis.io/collections/launchdarkly/open-launchdarkly-tags-api/)
- …and 3 more published on APIs.io

#### Overlays (29)

OpenAPI overlays, including conversational phrasing for each operation.

- [Launchdarkly Access Tokens Api Phrasing Overlay](https://apis.io/overlays/launchdarkly/launchdarkly-access-tokens-api-phrasing-overlay/)
- [Launchdarkly Account Members Api Phrasing Overlay](https://apis.io/overlays/launchdarkly/launchdarkly-account-members-api-phrasing-overlay/)
- [Launchdarkly Approvals Api Phrasing Overlay](https://apis.io/overlays/launchdarkly/launchdarkly-approvals-api-phrasing-overlay/)
- [Launchdarkly Audit Log Api Phrasing Overlay](https://apis.io/overlays/launchdarkly/launchdarkly-audit-log-api-phrasing-overlay/)
- [Launchdarkly Backup Api Phrasing Overlay](https://apis.io/overlays/launchdarkly/launchdarkly-backup-api-phrasing-overlay/)
- [Launchdarkly Client Side Evaluation Api Phrasing Overlay](https://apis.io/overlays/launchdarkly/launchdarkly-client-side-evaluation-api-phrasing-overlay/)
- [Launchdarkly Client Side Streaming Api Phrasing Overlay](https://apis.io/overlays/launchdarkly/launchdarkly-client-side-streaming-api-phrasing-overlay/)
- [Launchdarkly Code References Api Phrasing Overlay](https://apis.io/overlays/launchdarkly/launchdarkly-code-references-api-phrasing-overlay/)
- [Launchdarkly Custom Roles Api Phrasing Overlay](https://apis.io/overlays/launchdarkly/launchdarkly-custom-roles-api-phrasing-overlay/)
- [Launchdarkly Debug Sessions Api Phrasing Overlay](https://apis.io/overlays/launchdarkly/launchdarkly-debug-sessions-api-phrasing-overlay/)
- [Launchdarkly Environments Api Phrasing Overlay](https://apis.io/overlays/launchdarkly/launchdarkly-environments-api-phrasing-overlay/)
- [Launchdarkly Experiments Api Phrasing Overlay](https://apis.io/overlays/launchdarkly/launchdarkly-experiments-api-phrasing-overlay/)
- [Launchdarkly Feature Flags Api Phrasing Overlay](https://apis.io/overlays/launchdarkly/launchdarkly-feature-flags-api-phrasing-overlay/)
- [Launchdarkly Flag Triggers Api Phrasing Overlay](https://apis.io/overlays/launchdarkly/launchdarkly-flag-triggers-api-phrasing-overlay/)
- [Launchdarkly Integration Audit Log Subscriptions Api Phrasing Overlay](https://apis.io/overlays/launchdarkly/launchdarkly-integration-audit-log-subscriptions-api-phrasing-overlay/)
- [Launchdarkly Metrics Api Phrasing Overlay](https://apis.io/overlays/launchdarkly/launchdarkly-metrics-api-phrasing-overlay/)
- [Launchdarkly Php Polling Api Phrasing Overlay](https://apis.io/overlays/launchdarkly/launchdarkly-php-polling-api-phrasing-overlay/)
- [Launchdarkly Projects Api Phrasing Overlay](https://apis.io/overlays/launchdarkly/launchdarkly-projects-api-phrasing-overlay/)
- [Launchdarkly Relay Proxy Configurations Api Phrasing Overlay](https://apis.io/overlays/launchdarkly/launchdarkly-relay-proxy-configurations-api-phrasing-overlay/)
- [Launchdarkly Releases Api Phrasing Overlay](https://apis.io/overlays/launchdarkly/launchdarkly-releases-api-phrasing-overlay/)
- [Launchdarkly Rest Api Overlay](https://apis.io/overlays/launchdarkly/launchdarkly-rest-api-overlay/)
- [Launchdarkly Segments Api Phrasing Overlay](https://apis.io/overlays/launchdarkly/launchdarkly-segments-api-phrasing-overlay/)
- [Launchdarkly Server Side Evaluation Api Phrasing Overlay](https://apis.io/overlays/launchdarkly/launchdarkly-server-side-evaluation-api-phrasing-overlay/)
- [Launchdarkly Server Side Streaming Api Phrasing Overlay](https://apis.io/overlays/launchdarkly/launchdarkly-server-side-streaming-api-phrasing-overlay/)
- [Launchdarkly Status Api Phrasing Overlay](https://apis.io/overlays/launchdarkly/launchdarkly-status-api-phrasing-overlay/)
- …and 4 more published on APIs.io

#### Governance rules (2)

Spectral rulesets for the provider's contracts.

- [LaunchDarkly — asyncapi rules](https://apis.io/rules/launchdarkly/launchdarkly-asyncapi-spectral-rules/)
- [LaunchDarkly — jsonschema rules](https://apis.io/rules/launchdarkly/launchdarkly-jsonschema-spectral-rules/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Launchdarkly Authentication](https://apis.io/security/launchdarkly/launchdarkly-authentication/)
- [Launchdarkly Domain Security](https://apis.io/security/launchdarkly/launchdarkly-domain-security/)
- [Launchdarkly Trust Center](https://apis.io/security/launchdarkly/launchdarkly-trust-center/)
- [Launchdarkly Vulnerability Disclosure](https://apis.io/security/launchdarkly/launchdarkly-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Launchdarkly Scopes](https://apis.io/scopes/launchdarkly/launchdarkly-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Launchdarkly Plans Pricing](https://apis.io/plans/launchdarkly/launchdarkly-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Launchdarkly Rate Limits](https://apis.io/rate-limits/launchdarkly/launchdarkly-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Launchdarkly Finops](https://apis.io/finops/launchdarkly/launchdarkly-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.launchdarkly.com/)
- [Documentation](https://launchdarkly.com/docs/home)
- [Getting started](https://launchdarkly.com/docs/home/getting-started)
- [API reference](https://launchdarkly.com/docs/api)
- [Pricing](https://launchdarkly.com/pricing/)
- [Sign up](https://app.launchdarkly.com/signup)
- [Support](https://support.launchdarkly.com/)
- [Blog](https://launchdarkly.com/blog/feed/)
- [Terms of service](https://launchdarkly.com/policies/)
- [Privacy policy](https://launchdarkly.com/privacy/)
- [GitHub](https://github.com/launchdarkly)
- [Status](https://status.launchdarkly.com/)

## API Evangelist rating

**Kin Score 79.7** — exemplar · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 80.0 |
| Contract quality | 70.5 |
| Contract governance | 31.8 |
| Operational transparency | 92.1 |
| Developer ergonomics | 80.4 |
| Access clarity | 92.1 |

**Agent readiness 60.6** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | documented (partial credit) |
| MCP Server | verified |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | partial |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | derived (partial credit) |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | yes |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | yes |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | verified |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |
| Pagination Ratio | partial |
| Operation Distinctiveness | — |

**Regulatory alignment 45.1** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/launchdarkly/](https://apis.io/providers/launchdarkly/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for LaunchDarkly: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/launchdarkly/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
