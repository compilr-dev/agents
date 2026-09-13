---
title: "OTelSDK"
parent: Type Aliases
nav_order: 1
---


# Type Alias: OTelSDK

```ts
type OTelSDK = {
  trace: {
     getTracer: OTelTracer;
  };
};
```

Defined in: tracing/types.ts:246

OpenTelemetry SDK types (defined here to avoid importing optional dependency)

## Properties

### trace

```ts
trace: {
  getTracer: OTelTracer;
};
```

Defined in: tracing/types.ts:247

#### getTracer()

```ts
getTracer(name, version?): OTelTracer;
```

##### Parameters

| Parameter | Type |
| ------ | ------ |
| `name` | `string` |
| `version?` | `string` |

##### Returns

[`OTelTracer`](TypeAlias.OTelTracer.md)
