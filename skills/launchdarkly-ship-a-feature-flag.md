---
name: launchdarkly-ship-a-feature-flag
description: Create a feature flag in a LaunchDarkly project, target it in one environment, and turn it on — the core CodeControl loop, end to end.
api: launchdarkly:launchdarkly-feature-flags-api
generated: '2026-08-27'
method: generated
source: >-
  Grounded in openapi/launchdarkly-rest-api-openapi.json (harvested 2026-08-27 from
  https://app.launchdarkly.com/api/v2/openapi.json, HTTP 200). Every operationId below
  was verified present in that contract. Semantics from
  conventions/launchdarkly-conventions.yml.
operations:
  - getProjects
  - getProject
  - getEnvironment
  - postFeatureFlag
  - getFeatureFlag
  - patchFeatureFlag
  - getFeatureFlagStatus
---

# Ship a feature flag

Base URL `https://app.launchdarkly.com` (federal: `https://app.launchdarkly.us`, EU: `https://app.eu.launchdarkly.com`).

## Before you start

Send these on **every** request:

```
Authorization: <your access token>     # NO "Bearer " prefix. This is the #1 mistake.
LD-API-Version: 20240415
Content-Type: application/json
```

An SDK key, mobile key or client-side ID will return `401` here. Only a personal or service access token works.

## Step 1 — find the project and environment

`getProjects` → `GET /api/v2/projects`. Paginated, default limit 20; use `limit` and `offset`.

`getEnvironment` → `GET /api/v2/projects/{projectKey}/environments/{environmentKey}`.

A flag is defined **once per project** but configured **separately per environment**. You need both keys for everything that follows. Keys are customer-authored strings, not opaque IDs — do not guess them.

## Step 2 — create the flag

`postFeatureFlag` → `POST /api/v2/flags/{projectKey}`

```json
{
  "key": "example-feature",
  "name": "Example feature",
  "description": "Guards the new checkout flow",
  "variations": [{ "value": true }, { "value": false }],
  "temporary": true,
  "tags": ["checkout"]
}
```

A new flag is **off in every environment** by default. Creating it is safe.

There is **no idempotency key on this API**. If the connection drops, do not blind-retry the POST — call `getFeatureFlag` (`GET /api/v2/flags/{projectKey}/{featureFlagKey}`) first. A duplicate create returns `400` with `"code": "invalid_request"` and the message `A feature with that key already exists`, which is recoverable, but a re-read is the correct move.

## Step 3 — target and turn it on

`patchFeatureFlag` → `PATCH /api/v2/flags/{projectKey}/{featureFlagKey}`

Use **semantic patch** for anything that changes behaviour. It is atomic — either every instruction applies or none do — which is the closest this API gets to a transaction.

```
Content-Type: application/json; domain-model=launchdarkly.semanticpatch
```

```json
{
  "comment": "Enable for the beta segment",
  "environmentKey": "production",
  "instructions": [
    { "kind": "addRule", "clauses": [ { "contextKind": "user", "attribute": "segmentMatch", "op": "segmentMatch", "values": ["beta-users"] } ], "variationId": "<variation id>" },
    { "kind": "turnFlagOn" }
  ]
}
```

Omit the `domain-model=` part of the Content-Type and the body is parsed as a JSON Patch and rejected with `400`.

If you only need to edit metadata (name, description, tags), plain JSON Patch (RFC 6902) is simpler:

```json
[{ "op": "replace", "path": "/description", "value": "Updated description" }]
```

Add a `test` op first to make the write conditional on the version you read:

```json
[
  { "op": "test", "path": "/version", "value": 10 },
  { "op": "replace", "path": "/description", "value": "Updated description" }
]
```

## Step 4 — confirm

`getFeatureFlagStatus` → `GET /api/v2/flag-statuses/{projectKey}/{environmentKey}/{featureFlagKey}` returns whether the flag is being evaluated and when it was last requested.

## Reversing this

- Wrong targeting: restore a previous version from change history. **The window is 30 days**, and you cannot restore into a state controlled by an experiment, guarded rollout or progressive rollout.
- Done with the flag but not sure: deprecate it (hidden from the live list, still evaluated, restorable) or archive it.
- `deleteFeatureFlag` is **terminal**. There is no undo. Check `getDependentFlags` (`GET /api/v2/flags/{projectKey}/{featureFlagKey}/dependent-flags`) first — prerequisites make flags a graph, and deleting one can change how others evaluate.

## Errors and limits

| Status | What it usually means here |
|---|---|
| 400 | Malformed JSON, or a semantic patch sent without the `domain-model` Content-Type |
| 401 | Bad token, or you sent `Bearer `, or you used an SDK key |
| 403 | Missing permission — **or** a beta resource called without `LD-API-Version: beta` |
| 409 | Concurrent modification. Retry, but re-read first (no idempotency key) |
| 429 | Rate limited. Read whichever `X-Ratelimit-*` headers are present; reset values are epoch **milliseconds**, `Retry-After` is **seconds** |

Errors are `{ "code", "message", "id" }` — not RFC 9457 problem+json. Keep the `id` for support.

**Do not use this API to read flag values at runtime.** SDK evaluation goes through streaming and a CDN, is never rate limited, and is the correct hot path. The REST API is for management.
