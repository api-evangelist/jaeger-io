---
title: "Making design decisions for ClickHouse as a core storage backend in Jaeger"
url: "https://medium.com/jaegertracing/making-design-decisions-for-clickhouse-as-a-core-storage-backend-in-jaeger-62bf90a979d?source=rss----99735986d50---4"
date: "2023-09-24"
author: "Ha Anh Vu"
feed_url: "https://medium.com/feed/jaegertracing"
---
Overview ClickHouse database has been used as a remote storage server for Jaeger traces for quite some time, thanks to a gRPC storage plugin built by the community . Lately, we have decided to make ClickHouse one of the core storage backends for Jaeger, besides Cassandra and Elasticsearch. The first step for this integration was figuring out an optimal schema design.
