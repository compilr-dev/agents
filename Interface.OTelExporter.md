---
title: "OTelExporter"
parent: Interfaces
nav_order: 1
---


# Interface: OTelExporter

Defined in: tracing/types.ts:234

OpenTelemetry exporter interface (simplified)
Allows integration with any OTel-compatible backend

## Properties

### name

```ts
name: string;
```

Defined in: tracing/types.ts:236

Exporter name for logging

## Methods

### export()

```ts
export(spans): Promise<void>;
```

Defined in: tracing/types.ts:238

Export spans

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `spans` | [`Span`](Interface.Span.md)[] |

#### Returns

`Promise`\<`void`\>

### shutdown()?

```ts
optional shutdown(): Promise<void>;
```

Defined in: tracing/types.ts:240

Shutdown the exporter

#### Returns

`Promise`\<`void`\>
