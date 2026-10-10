---
title: "createOTelExporter"
parent: Functions
nav_order: 1
---


# Function: createOTelExporter()

```ts
function createOTelExporter(tracerName?, tracerVersion?): Promise<OTelExporter>;
```

Defined in: tracing/otel.ts:98

Create an OpenTelemetry exporter that wraps OTel spans

This exporter converts our internal Span format to OpenTelemetry spans
and uses the configured OTel tracer to export them.

## Parameters

| Parameter | Type | Default value | Description |
| ------ | ------ | ------ | ------ |
| `tracerName` | `string` | `'agent-tracing'` | Name for the OTel tracer |
| `tracerVersion` | `string` | `'1.0.0'` | Version for the OTel tracer |

## Returns

`Promise`\<[`OTelExporter`](Interface.OTelExporter.md)\>

OTelExporter instance

## Example

```typescript
// First, set up OpenTelemetry in your application:
// import { NodeTracerProvider } from '@opentelemetry/sdk-trace-node';
// const provider = new NodeTracerProvider();
// provider.register();

// Then use with TracingManager:
const exporter = await createOTelExporter('my-agent', '1.0.0');
const tracingManager = new TracingManager({
  serviceName: 'my-agent',
  otelExporter: exporter,
});
```
