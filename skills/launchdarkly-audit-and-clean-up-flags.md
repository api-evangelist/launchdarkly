---
name: launchdarkly-audit-and-clean-up-flags
description: Find stale and unused feature flags across a LaunchDarkly project, check what depends on them, and retire them safely without deleting anything that is still live.
api: launchdarkly:launchdarkly-feature-flags-api
generated: '2026-08-27'
method: generated
source: >-
  Grounded in openapi/launchdarkly-rest-api-openapi.json (harvested 2026-08-27 from
  https://app.launchdarkly.com/api/v2/openapi.json, HTTP 200). Every operationId was
  verified present in that contract.
operations:
  - getFeatureFlags
  - getFeatureFlag
  - getFeatureFlagStatuses
  - getFeatureFlagStatus
  - getDependentFlags
  - patchFeatureFlag
  - deleteFeatureFlag
  - getAuditLogEntries
---

# Audit and retire stale flags

Flag debt is the standard failure mode of feature management. This is the read-heavy, low-risk half of the job — do all of it before you write anything.

## Step 1 — inventory

`getFeatureFlags` → `GET /api/v2/flags/{projectKey}`

Paginated since API version `20240415`, **default limit 20**. Page with `limit` and `offset` until `_links.next` is absent. Two things changed in that version and will bite an agent written against older examples:

- The `environments` field is only returned when you filter by environment with `filterEnv`.
- The `followerId`, `hasDataExport`, `status`, `contextKindTargeted` and `segmentTargeted` filters were removed, along with the `compare` parameter.

Each flag carries `creationDate`, `archivedDate`, `deprecatedDate` and a `stale` object — all epoch milliseconds. That is your staleness signal straight from the definition.

## Step 2 — check whether anything is still evaluating it

`getFeatureFlagStatuses` → `GET /api/v2/flag-statuses/{projectKey}/{environmentKey}`

Returns per-flag evaluation status and last-requested time for the whole environment in one call. **Run this for every environment**, not just production. A flag idle in production may be load-bearing in staging.

## Step 3 — check what depends on it

`getDependentFlags` → `GET /api/v2/flags/{projectKey}/{featureFlagKey}/dependent-flags`

Prerequisites make flags a directed graph. A flag with dependents is not stale no matter how long it has been since anyone touched it — removing it changes how the flags above it evaluate. **A non-empty response here ends the audit for that flag.**

## Step 4 — retire, in increasing order of finality

Use semantic patch on `patchFeatureFlag` (`Content-Type: application/json; domain-model=launchdarkly.semanticpatch`) with a comment on every call.

1. **Deprecate** — hides the flag from the live list, keeps evaluating it, fully restorable. Client-side flags only. Start here.
2. **Archive** — retires it from active use, restorable from the archived list. The docs do not state how long an archived flag stays restorable, so do not assume a window.
3. **Delete** — `deleteFeatureFlag` → `DELETE /api/v2/flags/{projectKey}/{featureFlagKey}`. **Terminal. No undo, no restore, no window.** LaunchDarkly's own MCP server marks the equivalent tool `Destructive` and requires an explicit confirmation argument; hold an agent to at least that bar.

Restoring a previous flag *version* only reaches back **30 days**, and it cannot recover a deleted flag at all — it recovers a configuration, not an object.

## Step 5 — record it

`getAuditLogEntries` → `GET /api/v2/auditlog` confirms each change landed and preserves the comment you attached. Filter by date and by resource specifier to produce the cleanup report.

## Pacing

Auditing a large project is exactly the shape of workload that trips rate limits, and the **global limit is shared across every token on the account** — an aggressive audit degrades the API for everyone. Read `X-Ratelimit-Global-Remaining` and `X-Ratelimit-Route-Remaining` on each response and slow down before you get a 429 rather than after.
