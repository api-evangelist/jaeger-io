---
title: "Introducing native support for OpenTelemetry in Jaeger"
url: "https://medium.com/jaegertracing/introducing-native-support-for-opentelemetry-in-jaeger-eb661be8183c?source=rss----99735986d50---4"
date: "2022-05-30"
author: "Yuri Shkuro"
feed_url: "https://medium.com/feed/jaegertracing"
---
The latest Jaeger v1.35 release introduced the ability to receive OpenTelemetry trace data via the OpenTelemetry Protocol (OTLP) , which all OpenTelemetry SDKs are required to support. This is a follow-up to the previous announcement to retire Jaeger’s “classic” client libraries. With this new capability, it is no longer necessary to use the Jaeger exporters with the OpenTelemetry SDKs, or to run the OpenTelemetry Collector in front of the Jaeger backend.
