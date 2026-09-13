---
title: "createMultiExporter"
parent: Functions
nav_order: 1
---


# Function: createMultiExporter()

```ts
function createMultiExporter(exporters): OTelExporter;
```

Defined in: tracing/otel.ts:287

Create a multi-exporter that sends to multiple backends

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `exporters` | [`OTelExporter`](Interface.OTelExporter.md)[] | List of exporters to use |

## Returns

[`OTelExporter`](Interface.OTelExporter.md)

OTelExporter instance

## Example

```typescript
const multiExporter = createMultiExporter([
  createConsoleExporter(),
  await createOTelExporter(),
]);
```
