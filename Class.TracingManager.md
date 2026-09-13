---
title: "TracingManager"
parent: Classes
nav_order: 1
---


# Class: TracingManager

Defined in: tracing/manager.ts:55

Manages distributed tracing for agent operations

## Example

```typescript
const tracing = new TracingManager({
  serviceName: 'my-agent',
  defaultAttributes: { environment: 'production' },
});

// Start a trace
const traceId = tracing.startTrace();

// Create spans
const span = tracing.startSpan({ name: 'process-request' });
span.attributes['request.id'] = '123';

// End span and trace
tracing.endSpan(span.spanId, { status: 'ok' });
const trace = tracing.endTrace(traceId);
```

## Implements

- [`TracingManagerInterface`](Interface.TracingManagerInterface.md)

## Constructors

### Constructor

```ts
new TracingManager(options?): TracingManager;
```

Defined in: tracing/manager.ts:77

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `options` | [`TracingManagerOptions`](Interface.TracingManagerOptions.md) |

#### Returns

`TracingManager`

## Methods

### addSpanEvent()

```ts
addSpanEvent(
   spanId, 
   name, 
   attributes?): void;
```

Defined in: tracing/manager.ts:358

Add an event to a span

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `spanId` | `string` | Span ID |
| `name` | `string` | Event name |
| `attributes?` | [`SpanAttributes`](TypeAlias.SpanAttributes.md) | Event attributes |

#### Returns

`void`

#### Implementation of

[`TracingManagerInterface`](Interface.TracingManagerInterface.md).[`addSpanEvent`](Interface.TracingManagerInterface.md#addspanevent)

### clear()

```ts
clear(): void;
```

Defined in: tracing/manager.ts:539

Clear all traces and spans

#### Returns

`void`

### clearTrace()

```ts
clearTrace(traceId): boolean;
```

Defined in: tracing/manager.ts:178

Clear a trace from memory

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `traceId` | `string` |

#### Returns

`boolean`

### endSpan()

```ts
endSpan(spanId, options?): Span | undefined;
```

Defined in: tracing/manager.ts:283

End a span

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `spanId` | `string` | Span ID to end |
| `options?` | [`EndSpanOptions`](Interface.EndSpanOptions.md) | End options |

#### Returns

[`Span`](Interface.Span.md) \| `undefined`

Ended span or undefined if not found

#### Implementation of

[`TracingManagerInterface`](Interface.TracingManagerInterface.md).[`endSpan`](Interface.TracingManagerInterface.md#endspan)

### endTrace()

```ts
endTrace(traceId): Trace | undefined;
```

Defined in: tracing/manager.ts:131

End a trace and optionally export it

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `traceId` | `string` | Trace ID to end |

#### Returns

[`Trace`](Interface.Trace.md) \| `undefined`

Completed trace or undefined if not found

#### Implementation of

[`TracingManagerInterface`](Interface.TracingManagerInterface.md).[`endTrace`](Interface.TracingManagerInterface.md#endtrace)

### export()

```ts
export(traceId): Promise<void>;
```

Defined in: tracing/manager.ts:490

Manually export a trace

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `traceId` | `string` |

#### Returns

`Promise`\<`void`\>

### getActiveTraces()

```ts
getActiveTraces(): Trace[];
```

Defined in: tracing/manager.ts:171

Get all active traces

#### Returns

[`Trace`](Interface.Trace.md)[]

### getCurrentContext()

```ts
getCurrentContext(): SpanContext | undefined;
```

Defined in: tracing/manager.ts:337

Get current span context for propagation

#### Returns

[`SpanContext`](Interface.SpanContext.md) \| `undefined`

### getCurrentSpan()

```ts
getCurrentSpan(): Span | undefined;
```

Defined in: tracing/manager.ts:328

Get the current active span

#### Returns

[`Span`](Interface.Span.md) \| `undefined`

#### Implementation of

[`TracingManagerInterface`](Interface.TracingManagerInterface.md).[`getCurrentSpan`](Interface.TracingManagerInterface.md#getcurrentspan)

### getSpan()

```ts
getSpan(spanId): Span | undefined;
```

Defined in: tracing/manager.ts:321

Get a span by ID

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `spanId` | `string` |

#### Returns

[`Span`](Interface.Span.md) \| `undefined`

### getStats()

```ts
getStats(): {
  activeSpans: number;
  activeTraces: number;
  totalSpans: number;
};
```

Defined in: tracing/manager.ts:524

Get tracing statistics

#### Returns

```ts
{
  activeSpans: number;
  activeTraces: number;
  totalSpans: number;
}
```

| Name | Type | Defined in |
| ------ | ------ | ------ |
| `activeSpans` | `number` | tracing/manager.ts:527 |
| `activeTraces` | `number` | tracing/manager.ts:525 |
| `totalSpans` | `number` | tracing/manager.ts:526 |

### getTrace()

```ts
getTrace(traceId): Trace | undefined;
```

Defined in: tracing/manager.ts:164

Get a trace by ID

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `traceId` | `string` |

#### Returns

[`Trace`](Interface.Trace.md) \| `undefined`

#### Implementation of

[`TracingManagerInterface`](Interface.TracingManagerInterface.md).[`getTrace`](Interface.TracingManagerInterface.md#gettrace)

### onEvent()

```ts
onEvent(handler): () => void;
```

Defined in: tracing/manager.ts:445

Subscribe to tracing events

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `handler` | [`TracingEventHandler`](TypeAlias.TracingEventHandler.md) | Event handler |

#### Returns

Unsubscribe function

() => `void`

### recordError()

```ts
recordError(spanId, error): void;
```

Defined in: tracing/manager.ts:414

Record an error on a span

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `spanId` | `string` | Span ID |
| `error` | `Error` | Error to record |

#### Returns

`void`

### setSpanAttributes()

```ts
setSpanAttributes(spanId, attributes): void;
```

Defined in: tracing/manager.ts:384

Set attributes on a span

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `spanId` | `string` | Span ID |
| `attributes` | [`SpanAttributes`](TypeAlias.SpanAttributes.md) | Attributes to set |

#### Returns

`void`

#### Implementation of

[`TracingManagerInterface`](Interface.TracingManagerInterface.md).[`setSpanAttributes`](Interface.TracingManagerInterface.md#setspanattributes)

### setSpanStatus()

```ts
setSpanStatus(
   spanId, 
   status, 
   message?): void;
```

Defined in: tracing/manager.ts:398

Set span status

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `spanId` | `string` | Span ID |
| `status` | [`SpanStatus`](TypeAlias.SpanStatus.md) | Status |
| `message?` | `string` | Optional status message |

#### Returns

`void`

#### Implementation of

[`TracingManagerInterface`](Interface.TracingManagerInterface.md).[`setSpanStatus`](Interface.TracingManagerInterface.md#setspanstatus)

### startSpan()

```ts
startSpan(options): Span;
```

Defined in: tracing/manager.ts:201

Start a new span

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `options` | [`StartSpanOptions`](Interface.StartSpanOptions.md) | Span options |

#### Returns

[`Span`](Interface.Span.md)

Created span

#### Implementation of

[`TracingManagerInterface`](Interface.TracingManagerInterface.md).[`startSpan`](Interface.TracingManagerInterface.md#startspan)

### startTrace()

```ts
startTrace(attributes?): string;
```

Defined in: tracing/manager.ts:104

Start a new trace

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `attributes?` | [`SpanAttributes`](TypeAlias.SpanAttributes.md) | Additional trace-level attributes |

#### Returns

`string`

Trace ID

#### Implementation of

[`TracingManagerInterface`](Interface.TracingManagerInterface.md).[`startTrace`](Interface.TracingManagerInterface.md#starttrace)
