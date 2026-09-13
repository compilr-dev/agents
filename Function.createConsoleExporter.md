---
title: "createConsoleExporter"
parent: Functions
nav_order: 1
---


# Function: createConsoleExporter()

```ts
function createConsoleExporter(options?): OTelExporter;
```

Defined in: tracing/otel.ts:163

Create a console exporter for debugging

This exporter simply logs spans to the console in a readable format.
Useful for development and debugging.

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `options` | \{ `output?`: (`message`) => `void`; `prettyPrint?`: `boolean`; \} | Console exporter options |
| `options.output?` | (`message`) => `void` | - |
| `options.prettyPrint?` | `boolean` | - |

## Returns

[`OTelExporter`](Interface.OTelExporter.md)

OTelExporter instance

## Example

```typescript
const exporter = createConsoleExporter({ prettyPrint: true });
const tracingManager = new TracingManager({
  serviceName: 'my-agent',
  otelExporter: exporter,
});
```
