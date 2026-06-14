# LaunchDarkly GraphQL Schema

## Overview

LaunchDarkly does not publish a native GraphQL API. This is a conceptual GraphQL schema derived from the LaunchDarkly REST API (version 20240415) data model documented at https://apidocs.launchdarkly.com/. The schema faithfully represents the resource types, relationships, and field structures found in the REST API, expressed in GraphQL SDL.

- **Source**: REST API data model — https://apidocs.launchdarkly.com/
- **Schema file**: launchdarkly-schema.graphql
- **Schema type**: Conceptual (REST-derived)
- **API version**: 20240415

## Types

The schema covers 40 named types across all major LaunchDarkly product areas:

### Feature Management

| Type | Description |
|---|---|
| `FeatureFlag` | A feature flag with its variations, defaults, and per-environment configurations |
| `FlagConfig` | The configuration of a feature flag within a specific environment (targeting rules, on/off state) |
| `Variation` | A single variation value (boolean, string, number, or JSON) of a feature flag |
| `FlagDefaults` | The default on/off variation indices for a flag |
| `MigrationSettings` | Settings for migration flags, tracking stage progression |
| `FlagTrigger` | A trigger that allows external services to toggle flags via unique webhook URLs |

### Targeting

| Type | Description |
|---|---|
| `Target` | An explicit list of context keys assigned to a specific variation |
| `Rule` | A targeting rule composed of clauses that evaluates to a variation or rollout |
| `Clause` | A single condition within a rule (attribute, operator, values) |
| `Rollout` | A percentage rollout assigning traffic weights to variations |
| `WeightedVariation` | A variation with an assigned traffic weight percentage |
| `Fallthrough` | The default rule applied when no other targeting rules match |
| `Prerequisite` | A dependency on another flag's variation before this flag evaluates |
| `ExperimentAllocation` | Configuration for experiment traffic allocation within a rollout |

### Segmentation

| Type | Description |
|---|---|
| `Segment` | A named group of contexts used for feature flag targeting |
| `SegmentTarget` | An explicit include/exclude list for a specific context kind within a segment |
| `SegmentRule` | A rule within a segment that dynamically includes contexts based on attributes |

### Experimentation

| Type | Description |
|---|---|
| `Metric` | A measurable event used to evaluate experiment outcomes |
| `MetricUrl` | A URL matcher for page-view or click metrics |
| `Experiment` | An A/B or multivariate experiment tied to a feature flag and metric |
| `ExperimentIteration` | A single run of an experiment with start/end dates and results |
| `ExperimentTreatment` | A variation used in an experiment with its allocation percentage |
| `MetricInput` | A metric reference within an experiment, indicating primary or secondary role |
| `ExperimentInfo` | Summary of experiment configuration attached to a feature flag |

### Project & Environment

| Type | Description |
|---|---|
| `Project` | A top-level organizational container for flags, environments, and metrics |
| `Environment` | A deployment context (e.g., production, staging) within a project |
| `ClientSideAvailability` | Controls whether a flag is available to client-side SDKs |
| `ApprovalSettings` | Per-environment configuration for change approval workflows |

### Governance & Approvals

| Type | Description |
|---|---|
| `ApprovalRequest` | A request for review before applying a flag change |
| `ApprovalReview` | An individual review action (approve, decline, comment) on an approval request |
| `AuditLogEntry` | An immutable record of a change made to any LaunchDarkly resource |
| `AuditSubject` | The resource affected by an audit log action |
| `AuditTarget` | Parent or target resource context within an audit log entry |
| `Workflow` | A multi-stage automation sequence for scheduled or approval-gated flag changes |
| `WorkflowStage` | A single step within a workflow with conditions and an action |
| `WorkflowCondition` | A condition that gates progression to the next workflow stage |

### Integrations & Webhooks

| Type | Description |
|---|---|
| `Webhook` | An HTTP endpoint that receives POST notifications on LaunchDarkly events |
| `Statement` | A policy statement granting or denying access to resources and actions |
| `IntegrationSubscription` | A subscription to audit log events forwarded to an external integration |
| `IntegrationStatus` | Health status of an integration subscription |

### Identity & Access

| Type | Description |
|---|---|
| `AccessToken` | A personal or service API token used to authenticate REST requests |
| `Member` | An account user with a role, team memberships, and custom role grants |
| `Team` | A group of members sharing permissions and project access |
| `TeamProject` | A project-level permission scope for a team |
| `PermissionGrant` | An inline permission grant within a team or member record |
| `CustomRole` | A named set of policy statements defining fine-grained permissions |

### Infrastructure

| Type | Description |
|---|---|
| `RelayProxyConfig` | Configuration for a LaunchDarkly Relay Proxy auto-configuration entry |
| `ReleasePipeline` | An ordered sequence of release phases for coordinated flag rollouts |
| `ReleasePhase` | A stage within a release pipeline targeting specific environments |
| `ReleaseAudience` | An environment-and-segment audience within a release phase |
| `CodeReferenceRepository` | A source code repository scanned for feature flag references |
| `BigSegmentStore` | A persistent store backing large-scale (unbounded) segments |

## Queries

The `Query` type exposes read operations across all resource domains:

- `projects` / `project(projectKey)` — list and retrieve projects
- `environments(projectKey)` / `environment(projectKey, environmentKey)` — manage environments
- `featureFlags(projectKey, environmentKey, tags)` / `featureFlag(projectKey, featureFlagKey)` — flag access
- `segments(projectKey, environmentKey)` / `segment(...)` — segment access
- `metrics(projectKey)` / `metric(projectKey, metricKey)` — metric access
- `experiments(projectKey, environmentKey)` / `experiment(...)` — experiment access
- `approvalRequests(...)` / `approvalRequest(id)` — approval workflow queries
- `auditLog(before, after, q, limit)` — paginated audit log access
- `webhooks` / `webhook(webhookId)` — webhook configuration
- `integrationSubscriptions(integrationKey)` — integration management
- `accessTokens` / `accessToken(tokenId)` — token management
- `teams` / `team(teamKey)` — team queries
- `members` / `member(memberId)` — member queries
- `customRoles` / `customRole(customRoleKey)` — custom role queries
- `relayProxyConfigs` / `relayProxyConfig(id)` — relay proxy configuration
- `releasePipelines(projectKey)` / `releasePipeline(...)` — release pipeline queries
- `workflows(projectKey, featureFlagKey, environmentKey)` — workflow queries
- `flagTriggers(...)` — flag trigger queries
- `codeReferenceRepositories` — code reference repository listing
- `tags(projectKey)` — tag collection

## Mutations

The `Mutation` type covers create, update, and delete operations for all major resources:

- Feature flag CRUD and toggle operations
- Project and environment management
- Segment management
- Metric and experiment lifecycle
- Approval request creation, review, and application
- Webhook and integration management
- Access token creation and reset
- Team, member, and custom role management
- Relay proxy configuration management
- Workflow and flag trigger management

## Enums

| Enum | Values |
|---|---|
| `FlagKind` | `BOOLEAN`, `MULTIVARIATE` |
| `VariationType` | `BOOLEAN`, `STRING`, `NUMBER`, `JSON` |
| `RolloutKind` | `ROLLOUT`, `EXPERIMENT` |
| `MetricKind` | `PAGE_VIEW`, `CLICK`, `CUSTOM` |
| `ExperimentStatus` | `CREATED`, `RUNNING`, `STOPPED`, `ARCHIVED` |
| `ApprovalStatus` | `PENDING`, `APPROVED`, `DECLINED`, `APPLIED`, `FAILED` |
| `ApprovalReviewKind` | `APPROVE`, `DECLINE`, `COMMENT` |
| `WorkflowKind` | `CUSTOM`, `RELEASE` |
| `TokenType` | `PERSONAL`, `SERVICE` |
| `MigrationStage` | `OFF`, `DUALWRITE`, `SHADOW`, `LIVE`, `RAMPDOWN`, `COMPLETE` |
| `ClauseOp` | `IN`, `END_WITH`, `START_WITH`, `MATCHES`, `CONTAINS`, `LESS_THAN`, `LESS_THAN_OR_EQUAL`, `GREATER_THAN`, `GREATER_THAN_OR_EQUAL`, `BEFORE`, `AFTER`, `SEGMENT_MATCH`, `SEMANTIC_VERSION_*` |

## References

- REST API Documentation: https://apidocs.launchdarkly.com/
- OpenAPI Specification: ../openapi/launchdarkly-rest-api-openapi.yml
- GitHub Organization: https://github.com/launchdarkly
