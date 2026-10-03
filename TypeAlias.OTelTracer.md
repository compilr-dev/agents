---
title: "OTelTracer"
parent: Type Aliases
nav_order: 1
---


# Type Alias: OTelTracer

```ts
type OTelTracer = {
  startSpan: OTelSpan;
};
```

Defined in: tracing/types.ts:252

## Methods

### startSpan()

```ts
startSpan(name, options?): OTelSpan;
```

Defined in: tracing/types.ts:253

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `name` | `string` |
| `options?` | `unknown` |

#### Returns

[`OTelSpan`](TypeAlias.OTelSpan.md)
