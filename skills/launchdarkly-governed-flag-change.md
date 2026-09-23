---
name: launchdarkly-governed-flag-change
description: Propose a flag change through approvals or schedule it for a future date, instead of applying it directly — the safe write path for an agent operating in production.
api: launchdarkly:launchdarkly-approvals-api
generated: '2026-08-27'
method: generated
source: >-
  Grounded in openapi/launchdarkly-rest-api-openapi.json (harvested 2026-08-27 from
  https://app.launchdarkly.com/api/v2/openapi.json, HTTP 200). Every operationId was
  verified present. Entitlement notes from plans/launchdarkly-plans-pricing.yml.
operations:
  - postApprovalRequest
  - getApprovalRequests
  - getApprovalRequest
  - postApprovalRequestApply
  - deleteApprovalRequest
  - postFlagConfigScheduledChanges
  - getFlagConfigScheduledChanges
  - deleteFlagConfigScheduledChanges
  - getAuditLogEntries
---

# Change a flag under governance

`patchFeatureFlag` applies immediately. These two paths let an agent **propose** a change instead — separating the decision from the execution, which is what makes an autonomous write reviewable.

Both are **Enterprise** features. On Developer and Foundation these endpoints exist in the contract but will fail on entitlement. Check the account's plan before building a flow that depends on them.

## Path A — approval request

`postApprovalRequest` → `POST /api/v2/approval-requests`

The body carries the same `instructions` array a semantic patch would, plus the reviewers who must sign off:

```json
{
  "description": "Enable example-feature for beta users",
  "instructions": [{ "kind": "turnFlagOn" }],
  "notifyMemberIds": ["<member id>"],
  "projectKey": "default",
  "environmentKey": "production",
  "flagKey": "example-feature"
}
```

Then:

- `getApprovalRequests` → `GET /api/v2/approval-requests` to poll, or `getApprovalRequest` → `GET /api/v2/approval-requests/{id}` for one.
- `postApprovalRequestApply` → `POST /api/v2/approval-requests/{id}/apply` once it is approved. **Nothing changes until this call.**
- `deleteApprovalRequest` → `DELETE /api/v2/approval-requests/{id}` withdraws it. This is the reversal, and it works right up until apply.

An agent should stop at the request and let a human approve. Do not call `apply` on your own request unless you were explicitly told to.

## Path B — scheduled change

`postFlagConfigScheduledChanges` → `POST /api/v2/projects/{projectKey}/flags/{featureFlagKey}/environments/{environmentKey}/scheduled-changes`

```json
{
  "executionDate": 1767225600000,
  "instructions": [{ "kind": "turnFlagOff" }]
}
```

`executionDate` is **Unix epoch milliseconds**, like every timestamp in this API. It is not ISO 8601.

- `getFlagConfigScheduledChanges` lists what is pending on that flag and environment.
- `deleteFlagConfigScheduledChanges` → `DELETE .../scheduled-changes/{id}` cancels it.

**The cancellation window closes when the date passes.** After execution there is no scheduled change left to delete, and — importantly — you also cannot restore a flag version that predates a scheduled change whose target date has already passed. Reversal gets harder, not easier, once the clock runs out.

## Confirm what happened

`getAuditLogEntries` → `GET /api/v2/auditlog` returns the change record for every mutation, including who or what made it and any `comment` you attached. Always attach a comment: it flows into the audit log, outgoing webhooks and integrations, and it is the only place an agent can explain itself after the fact.

```json
{ "comment": "Auto-disabled after error rate exceeded guardrail", "instructions": [{ "kind": "turnFlagOff" }] }
```

## Why this path exists

The direct `patchFeatureFlag` write has no idempotency key, no dry-run parameter, and a 30-day reversal window that experiments and guarded rollouts can void. An approval request has none of those problems, because the risky part does not happen until a human calls apply.
