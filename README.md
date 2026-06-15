# launchdarkly (launchdarkly)

LaunchDarkly is a feature management platform that enables development teams to deliver and control software through feature flags, allowing them to test in production and roll out features safely.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/launchdarkly/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/launchdarkly/refs/heads/main/apis.yml)

## Timestamps

- **Modified:** 2026-05-19

## APIs

### LaunchDarkly REST API

The LaunchDarkly REST API provides programmatic access to the full LaunchDarkly feature management platform. Developers can create, update, and manage feature flags, targeting rules, user segments, projects, environments, and team members. The API also supports scheduled flag changes, release pipelines, experimentation, approval workflows, and webhook integrations.

- **Human URL:** [https://apidocs.launchdarkly.com/](https://apidocs.launchdarkly.com/)
- **Base URL:** `https://app.launchdarkly.com/api/v2`

#### Tags

- Environments
- Experimentation
- Feature Flags
- Feature Management
- Segments
- Toggles

#### Properties

- [Documentation](https://apidocs.launchdarkly.com/)
- [OpenAPI](openapi/launchdarkly-rest-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/launchdarkly-rest-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/launchdarkly-rest-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### LaunchDarkly Webhooks API

The LaunchDarkly Webhooks API allows developers to build custom integrations that subscribe to activity events within LaunchDarkly. When actions occur such as flag changes, project creation, or environment modifications, LaunchDarkly sends HTTP POST payloads to configured webhook URLs. This enables use cases like updating external issue trackers, notifying support systems of feature rollouts, and triggering downstream automation workflows based on feature flag lifecycle events.

- **Human URL:** [https://launchdarkly.com/docs/api/webhooks](https://launchdarkly.com/docs/api/webhooks)
- **Base URL:** `https://app.launchdarkly.com/api/v2`

#### Tags

- Events
- Integrations
- Notifications
- Webhooks

#### Properties

- [Documentation](https://launchdarkly.com/docs/api/webhooks)
- [AsyncAPI](asyncapi/launchdarkly-webhooks-asyncapi.yml) — [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest)
- [Postman Collection](collections/launchdarkly-relay-proxy.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/launchdarkly-relay-proxy.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/launchdarkly-rest-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/launchdarkly-rest-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### LaunchDarkly Relay Proxy

The LaunchDarkly Relay Proxy is a small Go application that connects to the LaunchDarkly streaming API and proxies that connection to SDK clients within an organization's network. Instead of each server making outbound connections to LaunchDarkly's streaming service, multiple servers connect to the local Relay Proxy which maintains a single connection upstream.

- **Human URL:** [https://launchdarkly.com/docs/sdk/relay-proxy](https://launchdarkly.com/docs/sdk/relay-proxy)
- **Base URL:** `https://api.example.com`

#### Tags

- Edge
- Infrastructure
- Performance
- Proxy
- Streaming

#### Properties

- [Documentation](https://launchdarkly.com/docs/sdk/relay-proxy)
- [OpenAPI](openapi/launchdarkly-relay-proxy-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/launchdarkly-relay-proxy.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/launchdarkly-relay-proxy.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [GitHub Organization](https://github.com/launchdarkly)
- [LinkedIn](https://www.linkedin.com/company/launchdarkly)
- [JSON Schema](json-schema/launchdarkly-feature-flag-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/launchdarkly-webhook-event-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON-LD](json-ld/launchdarkly-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [Features](undefined)
- [L L Ms Txt](https://apidocs.launchdarkly.com/llms.txt)
