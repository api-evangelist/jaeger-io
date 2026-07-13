---
title: "Experiment: Migrating OpenTracing-based application in Go to use the OpenTelemetry SDK"
url: "https://medium.com/jaegertracing/experiment-migrating-opentracing-based-application-in-go-to-use-the-opentelemetry-sdk-29b09fe2fbc4?source=rss----99735986d50---4"
date: "2023-02-09"
author: "Yuri Shkuro"
feed_url: "https://medium.com/feed/jaegertracing"
---
TL;DR: This post explains how Jaeger’s 🚗 HotROD 🚗 app was migrated to the OpenTelemetry SDK. Jaeger’s HotROD demo has been around for a few years. It was written with OpenTracing-based instrumentation, including a couple of OSS libraries for HTTP and gRPC middleware, and used Jaeger’s native SDK for Go, jaeger-client-go .
