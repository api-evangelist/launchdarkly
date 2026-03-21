# LaunchDarkly (launchdarkly)
LaunchDarkly is a feature management platform that enables development teams to safely deploy, control, and measure software features at scale. Their developer platform provides REST APIs, webhook integrations, and a relay proxy for managing feature flags, targeting rules, user segments, experimentation, and release pipelines across environments.

**URL:** [Visit APIs.json URL](https://raw.githubusercontent.com/api-evangelist/launchdarkly/refs/heads/main/apis.yml)

## Scope

- **Type:** Contract
- **Position:** Consuming
- **Access:** 3rd-Party

## Tags:

 - Feature Flags, Feature Management, Experimentation, Toggles, Webhooks, Proxy

## Timestamps

- **Created:** 2025-03-05
- **Modified:** 2026-03-20

## APIs

### LaunchDarkly REST API
The LaunchDarkly REST API provides programmatic access to the full LaunchDarkly feature management platform. Developers can create, update, and manage feature flags, targeting rules, user segments, projects, environments, and team members. The API also supports scheduled flag changes, release pipelines, experimentation, approval workflows, and webhook integrations. Authentication is handled via personal or service access tokens, and the API follows a versioned scheme with the current default version being 20240415.

**Human URL:** [https://apidocs.launchdarkly.com/](https://apidocs.launchdarkly.com/)


#### Tags:

 - Feature Flags, Feature Management, Experimentation, Toggles, Segments, Environments

#### Properties

- [Documentation](https://apidocs.launchdarkly.com/)
- [OpenAPI](openapi/launchdarkly-rest-api-openapi.yml)

### LaunchDarkly Webhooks API
The LaunchDarkly Webhooks API allows developers to build custom integrations that subscribe to activity events within LaunchDarkly. When actions occur such as flag changes, project creation, or environment modifications, LaunchDarkly sends HTTP POST payloads to configured webhook URLs. This enables use cases like updating external issue trackers, notifying support systems of feature rollouts, and triggering downstream automation workflows based on feature flag lifecycle events.

**Human URL:** [https://launchdarkly.com/docs/api/webhooks](https://launchdarkly.com/docs/api/webhooks)


#### Tags:

 - Webhooks, Events, Integrations, Notifications

#### Properties

- [Documentation](https://launchdarkly.com/docs/api/webhooks)
- [AsyncAPI](asyncapi/launchdarkly-webhooks-asyncapi.yml)

### LaunchDarkly Relay Proxy
The LaunchDarkly Relay Proxy is a small Go application that connects to the LaunchDarkly streaming API and proxies that connection to SDK clients within an organization's network. Instead of each server making outbound connections to LaunchDarkly's streaming service, multiple servers connect to the local Relay Proxy which maintains a single connection upstream. It supports configuration for exporting metrics to Datadog, Stackdriver, and Prometheus, and can run in daemon mode for server-side SDKs that use a persistent data store.

**Human URL:** [https://launchdarkly.com/docs/sdk/relay-proxy](https://launchdarkly.com/docs/sdk/relay-proxy)


#### Tags:

 - Proxy, Streaming, Performance, Edge, Infrastructure

#### Properties

- [Documentation](https://launchdarkly.com/docs/sdk/relay-proxy)
- [OpenAPI](openapi/launchdarkly-relay-proxy-openapi.yml)

## Common Properties

- [Portal](https://launchdarkly.com/docs/)
- [Documentation](https://apidocs.launchdarkly.com/)
- [Website](https://launchdarkly.com/)
- [PrivacyPolicy](https://launchdarkly.com/policies/privacy/)
- [TermsOfService](https://launchdarkly.com/policies/terms-of-service/)
- [Blog](https://launchdarkly.com/blog/)
- [Login](https://app.launchdarkly.com/)

## Maintainers

**FN:** API Evangelist

**Email:** info@apievangelist.com
