---
title: "TracingManagerInterface"
parent: Interfaces
nav_order: 1
---


# Interface: TracingManagerInterface

Defined in: tracing/types.ts:371

Interface for TracingManager (for type references without circular deps)

## Methods

### addSpanEvent()

```ts
addSpanEvent(
   spanId, 
   name, 
   attributes?): void;
```

Defined in: tracing/types.ts:376

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `spanId` | `string` |
| `name` | `string` |
| `attributes?` | [`SpanAttributes`](TypeAlias.SpanAttributes.md) |

#### Returns

`void`

### endSpan()

```ts
endSpan(spanId, options?): Span | undefined;
```

Defined in: tracing/types.ts:375

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `spanId` | `string` |
| `options?` | [`EndSpanOptions`](Interface.EndSpanOptions.md) |

#### Returns

[`Span`](Interface.Span.md) \| `undefined`

### endTrace()

```ts
endTrace(traceId): Trace | undefined;
```

Defined in: tracing/types.ts:373

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `traceId` | `string` |

#### Returns

[`Trace`](Interface.Trace.md) \| `undefined`

### getCurrentSpan()

```ts
getCurrentSpan(): Span | undefined;
```

Defined in: tracing/types.ts:379

#### Returns

[`Span`](Interface.Span.md) \| `undefined`

### getTrace()

```ts
getTrace(traceId): Trace | undefined;
```

Defined in: tracing/types.ts:380

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `traceId` | `string` |

#### Returns

[`Trace`](Interface.Trace.md) \| `undefined`

### setSpanAttributes()

```ts
setSpanAttributes(spanId, attributes): void;
```

Defined in: tracing/types.ts:377

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `spanId` | `string` |
| `attributes` | [`SpanAttributes`](TypeAlias.SpanAttributes.md) |

#### Returns

`void`

### setSpanStatus()

```ts
setSpanStatus(
   spanId, 
   status, 
   message?): void;
```

Defined in: tracing/types.ts:378

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `spanId` | `string` |
| `status` | [`SpanStatus`](TypeAlias.SpanStatus.md) |
| `message?` | `string` |

#### Returns

`void`

### startSpan()

```ts
startSpan(options): Span;
```

Defined in: tracing/types.ts:374

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `options` | [`StartSpanOptions`](Interface.StartSpanOptions.md) |

#### Returns

[`Span`](Interface.Span.md)

### startTrace()

```ts
startTrace(attributes?): string;
```

Defined in: tracing/types.ts:372

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `attributes?` | [`SpanAttributes`](TypeAlias.SpanAttributes.md) |

#### Returns

`string`
