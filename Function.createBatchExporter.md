---
title: "createBatchExporter"
parent: Functions
nav_order: 1
---


# Function: createBatchExporter()

```ts
function createBatchExporter(innerExporter, options?): OTelExporter;
```

Defined in: tracing/otel.ts:217

Create a batch exporter that buffers spans and exports in batches

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `innerExporter` | [`OTelExporter`](Interface.OTelExporter.md) | The actual exporter to use |
| `options` | \{ `flushIntervalMs?`: `number`; `maxBatchSize?`: `number`; \} | Batch options |
| `options.flushIntervalMs?` | `number` | - |
| `options.maxBatchSize?` | `number` | - |

## Returns

[`OTelExporter`](Interface.OTelExporter.md)

OTelExporter instance

## Example

```typescript
const otelExporter = await createOTelExporter();
const batchExporter = createBatchExporter(otelExporter, {
  maxBatchSize: 100,
  flushIntervalMs: 5000,
});
```
