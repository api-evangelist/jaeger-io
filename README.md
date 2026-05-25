# Jaeger (jaeger-io)

Jaeger is an open-source, end-to-end distributed tracing platform for monitoring and troubleshooting transactions in complex distributed systems. Originally built and open-sourced by Uber Technologies in 2017, Jaeger was donated to the Cloud Native Computing Foundation, became an incubating project in 2017, and graduated in 2019. Jaeger v2 (November 2024) is a customized distribution of the OpenTelemetry Collector — the OTLP-native generation of the platform — and exposes three primary APIs: Query (read), Collector (span ingest), and Sampling Manager (remote sampling configuration).

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/jaeger-io/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=opensource-api-evangelist&utm_content=repo)

## Tags

 - Observability, Distributed Tracing, APM, OpenTelemetry, CNCF, Cloud Native, Microservices, Open Source

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## Governance

| | |
|---|---|
| Foundation | Cloud Native Computing Foundation (CNCF) |
| Maturity | Graduated (2019) |
| License | Apache 2.0 |
| Primary language | Go |
| Current major | v2 (built on OpenTelemetry Collector) |
| GitHub org | [jaegertracing](https://github.com/jaegertracing) |

## APIs

### Jaeger Query API
The read API for trace data. HTTP on port `16686`, gRPC on port `16685`. Endpoints to list services and operations, search traces (full and summary forms), fetch a trace by ID, and retrieve the inter-service dependency graph for a time range.

**Human URL:** [https://www.jaegertracing.io/docs/latest/apis/](https://www.jaegertracing.io/docs/latest/apis/)

- [Documentation](https://www.jaegertracing.io/docs/latest/apis/)
- [Protobuf — query_service.proto](https://github.com/jaegertracing/jaeger-idl/blob/main/proto/api_v3/query_service.proto)
- [OpenAPI](openapi/jaeger-query-api-openapi.yml)
- [JSON Schema — Span](json-schema/jaeger-span-schema.json)
- [JSON-LD Context](json-ld/jaeger-io-context.jsonld)
- [Naftiko Capability — Services and Operations](capabilities/query-services.yaml)
- [Naftiko Capability — Trace Search](capabilities/query-traces.yaml)
- [Naftiko Capability — Dependency Graph](capabilities/query-dependencies.yaml)

### Jaeger Collector API
The span ingest surface. Accepts native Jaeger `api_v2` over gRPC (`14250`) and HTTP (`14268`), OTLP over gRPC (`4317`) and HTTP (`4318`), and Zipkin v1/v2 on `9411`. Writes accepted spans to the configured storage backend.

**Human URL:** [https://www.jaegertracing.io/docs/latest/apis/](https://www.jaegertracing.io/docs/latest/apis/)

- [Protobuf — collector.proto](https://github.com/jaegertracing/jaeger-idl/blob/main/proto/api_v2/collector.proto)
- [OpenAPI](openapi/jaeger-collector-api-openapi.yml)
- [Naftiko Capability — Span Ingest](capabilities/collector-ingest.yaml)

### Jaeger Sampling Manager API
Distributes per-service sampling strategies to instrumented applications. HTTP on `5778`, gRPC on `5779`. Returns probabilistic, rate-limiting, or per-operation strategies — sourced from a static file or the adaptive sampling subsystem.

**Human URL:** [https://www.jaegertracing.io/docs/latest/sampling/](https://www.jaegertracing.io/docs/latest/sampling/)

- [Protobuf — sampling.proto](https://github.com/jaegertracing/jaeger-idl/blob/main/proto/api_v2/sampling.proto)
- [OpenAPI](openapi/jaeger-sampling-api-openapi.yml)
- [JSON Schema — Sampling Strategy](json-schema/jaeger-sampling-strategy-schema.json)
- [Naftiko Capability — Remote Sampling](capabilities/sampling-config.yaml)

## Ports at a glance

| Port | Protocol | Surface |
|---|---|---|
| 4317 | gRPC | OTLP receiver |
| 4318 | HTTP | OTLP receiver (`/v1/traces`) |
| 5778 | HTTP | Sampling Manager (`/sampling`, `/api/v2/samplingStrategy`) |
| 5779 | gRPC | Sampling Manager |
| 9411 | HTTP | Zipkin v1/v2 (`/api/v1/spans`, `/api/v2/spans`) |
| 14250 | gRPC | Jaeger api_v2 CollectorService |
| 14268 | HTTP | Jaeger legacy Thrift (`/api/traces`) |
| 16685 | gRPC | Query api_v3 / api_v2 |
| 16686 | HTTP | Query (`/api/v3/*`) + React UI |

## Components

- **Collector** — span ingest + write to storage. In v2, an OpenTelemetry Collector distribution.
- **Query** — read API + React UI.
- **Ingester** — optional Kafka consumer for the Kafka-buffered topology.
- **All-in-One** — single-binary dev distribution with in-memory storage.

## Storage backends

Cassandra · OpenSearch · Elasticsearch · ClickHouse · Kafka (buffer) · Badger (embedded)

## GitHub Org

- [jaegertracing/jaeger](https://github.com/jaegertracing/jaeger) — main Go monorepo (23k+ stars)
- [jaegertracing/jaeger-idl](https://github.com/jaegertracing/jaeger-idl) — proto + Thrift IDL, generated Go types, OpenAPI for api_v3
- [jaegertracing/jaeger-ui](https://github.com/jaegertracing/jaeger-ui) — React UI shipped with Query
- [jaegertracing/jaeger-operator](https://github.com/jaegertracing/jaeger-operator) — Kubernetes Operator
- [jaegertracing/helm-charts](https://github.com/jaegertracing/helm-charts) — Helm charts for Jaeger backend
- [jaegertracing/grafana-plugin](https://github.com/jaegertracing/grafana-plugin) — Grafana datasource + panel
- [jaegertracing/spark-dependencies](https://github.com/jaegertracing/spark-dependencies) — offline dependency-graph Spark job
- [jaegertracing/jaeger-clickhouse](https://github.com/jaegertracing/jaeger-clickhouse) — experimental ClickHouse storage plugin
- [jaegertracing/jaeger-vscode](https://github.com/jaegertracing/jaeger-vscode) — VS Code extension
- [jaegertracing/docker-protobuf](https://github.com/jaegertracing/docker-protobuf) — all-inclusive protoc image

The historical per-language Jaeger client libraries (`jaeger-client-go`, `-python`, `-java`, `-node`, `-cpp`, `-csharp`, `-js`) are archived; OpenTelemetry SDKs are the recommended instrumentation path.

## Artifacts

### OpenAPI

- [Jaeger Query API](openapi/jaeger-query-api-openapi.yml)
- [Jaeger Collector API](openapi/jaeger-collector-api-openapi.yml)
- [Jaeger Sampling Manager API](openapi/jaeger-sampling-api-openapi.yml)

### JSON Schema

- [Jaeger Span](json-schema/jaeger-span-schema.json)
- [Jaeger Sampling Strategy](json-schema/jaeger-sampling-strategy-schema.json)

### JSON-LD

- [Jaeger context](json-ld/jaeger-io-context.jsonld)

### Capabilities (Naftiko)

- [Query — Services and Operations](capabilities/query-services.yaml)
- [Query — Trace Search](capabilities/query-traces.yaml)
- [Query — Dependency Graph](capabilities/query-dependencies.yaml)
- [Collector — Span Ingest](capabilities/collector-ingest.yaml)
- [Sampling — Remote Sampling](capabilities/sampling-config.yaml)

### Vocabulary

- [Jaeger Vocabulary](vocabulary/jaeger-io-vocabulary.yml)

## Maintainers

**FN:** Kin Lane

**Email:** info@apievangelist.com
