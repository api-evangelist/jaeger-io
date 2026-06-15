# Jaeger (jaeger-io)

Jaeger is an open-source, end-to-end distributed tracing platform for monitoring and troubleshooting transactions in complex distributed systems. Originally built and open-sourced by Uber Technologies in 2017, Jaeger was donated to the Cloud Native Computing Foundation, became an incubating project in 2017, and graduated in 2019. Jaeger v2, released in November 2024, is a customized distribution of the OpenTelemetry Collector and is the OTLP-native generation of the platform. It exposes three primary APIs — the Query API (read), the Collector API (span ingest), and the Sampling Manager API (remote sampling configuration) — across HTTP and gRPC, supports six pluggable storage backends, and ships with a Kubernetes Operator, Helm charts, a React UI, and a Grafana plugin.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/jaeger-io/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/jaeger-io/refs/heads/main/apis.yml)

## Scope

- **Position:** Consuming
- **Access:** Open Source

## Tags

- Observability
- Distributed Tracing
- APM
- OpenTelemetry
- CNCF
- Cloud Native
- Microservices
- Open Source

## Timestamps

- **Created:** 2026-05-25T00:00:00.000Z
- **Modified:** 2026-05-25

## APIs

### Jaeger Query API

The Jaeger Query API (api_v3) exposes services, operations, trace search, single-trace lookup, and inter-service dependency graphs over HTTP (port 16686) and gRPC (port 16685). It is the OpenTelemetry-aligned successor to the legacy /api/* HTTP endpoints and powers the Jaeger UI.

- **Human URL:** [https://www.jaegertracing.io/docs/latest/apis/](https://www.jaegertracing.io/docs/latest/apis/)

#### Tags

- Observability
- Distributed Tracing
- Query

#### Properties

- [Documentation](https://www.jaegertracing.io/docs/latest/apis/)
- [Proto Buf](https://github.com/jaegertracing/jaeger-idl/blob/main/proto/api_v3/query_service.proto)
- [OpenAPI](openapi/jaeger-query-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/jaeger-query-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/jaeger-query-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/jaeger-span-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON-LD](json-ld/jaeger-io-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)

### Jaeger Collector API

The Jaeger Collector ingests spans over multiple protocols — native Jaeger api_v2 (gRPC 14250, HTTP 14268), OTLP (gRPC 4317, HTTP 4318), and Zipkin (HTTP 9411) — and writes them to the configured storage backend (Cassandra, OpenSearch, Elasticsearch, ClickHouse, Kafka, or Badger). In Jaeger v2 the Collector is a customized OpenTelemetry Collector distribution.

- **Human URL:** [https://www.jaegertracing.io/docs/latest/apis/](https://www.jaegertracing.io/docs/latest/apis/)

#### Tags

- Observability
- Distributed Tracing
- Ingest

#### Properties

- [Documentation](https://www.jaegertracing.io/docs/latest/apis/)
- [Proto Buf](https://github.com/jaegertracing/jaeger-idl/blob/main/proto/api_v2/collector.proto)
- [OpenAPI](openapi/jaeger-collector-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/jaeger-collector-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/jaeger-collector-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Jaeger Sampling Manager API

Remote sampling configuration API. Tracer SDKs poll the Sampling Manager (HTTP port 5778, gRPC port 5779) to retrieve the active per-service sampling strategy — probabilistic, rate-limiting, or per-operation. Backed by a static strategies file or by Jaeger's adaptive sampling subsystem.

- **Human URL:** [https://www.jaegertracing.io/docs/latest/sampling/](https://www.jaegertracing.io/docs/latest/sampling/)

#### Tags

- Observability
- Distributed Tracing
- Sampling

#### Properties

- [Documentation](https://www.jaegertracing.io/docs/latest/sampling/)
- [Proto Buf](https://github.com/jaegertracing/jaeger-idl/blob/main/proto/api_v2/sampling.proto)
- [OpenAPI](openapi/jaeger-sampling-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/jaeger-sampling-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/jaeger-sampling-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/jaeger-sampling-strategy-schema.json) — [JSON Schema](https://json-schema.org/specification)

## Common Properties

- [Portal](https://www.jaegertracing.io/)
- [Documentation](https://www.jaegertracing.io/docs/)
- [Documentation](https://www.jaegertracing.io/docs/latest/apis/)
- [Documentation](https://www.jaegertracing.io/docs/latest/architecture/)
- [Documentation](https://www.jaegertracing.io/docs/latest/deployment/)
- [Documentation](https://www.jaegertracing.io/docs/latest/sampling/)
- [Getting Started](https://www.jaegertracing.io/docs/latest/getting-started/)
- [GitHub Organization](https://github.com/jaegertracing)
- [Source Code](https://github.com/jaegertracing/jaeger)
- [Source Code](https://github.com/jaegertracing/jaeger-idl)
- [Source Code](https://github.com/jaegertracing/jaeger-ui)
- [Source Code](https://github.com/jaegertracing/jaeger-operator)
- [Source Code](https://github.com/jaegertracing/helm-charts)
- [Source Code](https://github.com/jaegertracing/spark-dependencies)
- [Source Code](https://github.com/jaegertracing/grafana-plugin)
- [Source Code](https://github.com/jaegertracing/jaeger-clickhouse)
- [Source Code](https://github.com/jaegertracing/jaeger-vscode)
- [Tool](https://github.com/jaegertracing/jaeger-operator)
- [Tool](https://github.com/jaegertracing/helm-charts)
- [Tool](https://github.com/jaegertracing/grafana-plugin)
- [Tool](https://github.com/jaegertracing/jaeger-vscode)
- [Container Image](https://hub.docker.com/u/jaegertracing)
- [License](https://github.com/jaegertracing/jaeger/blob/main/LICENSE)
- [Blog](https://medium.com/jaegertracing)
- [Forum](https://cloud-native.slack.com/archives/CGG7NFUJ3)
- [Sign Up](https://github.com/jaegertracing/jaeger/discussions)
- [Governance](https://github.com/jaegertracing/jaeger/blob/main/GOVERNANCE.md)
- [Maintainers](https://github.com/jaegertracing/jaeger/blob/main/MAINTAINERS.md)
- [Security Policy](https://github.com/jaegertracing/jaeger/blob/main/SECURITY.md)
- [Threat Model](https://github.com/jaegertracing/jaeger/blob/main/THREAT-MODEL.md)
- [Adopters](https://github.com/jaegertracing/jaeger/blob/main/ADOPTERS.md)
- [Changelog](https://github.com/jaegertracing/jaeger/blob/main/CHANGELOG.md)
- [Contributing Guide](https://github.com/jaegertracing/jaeger/blob/main/CONTRIBUTING.md)
- [Release Notes](https://github.com/jaegertracing/jaeger/releases)
- [Roadmap](https://github.com/orgs/jaegertracing/projects)
- [Organization](https://www.cncf.io/projects/jaeger/)
- [Documentation](https://github.com/open-telemetry/opentelemetry-proto)
- [Documentation](https://github.com/jaegertracing/jaeger-idl/tree/main/swagger/api_v3)
- [Features](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
**URL:** https://apievangelist.com
