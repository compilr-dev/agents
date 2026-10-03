---
title: "Span"
parent: Interfaces
nav_order: 1
---


# Interface: Span

Defined in: tracing/types.ts:38

A trace span representing a unit of work

## Properties

### attributes

```ts
attributes: SpanAttributes;
```

Defined in: tracing/types.ts:60

Span attributes

### durationMs?

```ts
optional durationMs?: number;
```

Defined in: tracing/types.ts:54

Duration in milliseconds (undefined if still active)

### endTime?

```ts
optional endTime?: number;
```

Defined in: tracing/types.ts:52

End time in milliseconds since epoch (undefined if still active)

### events

```ts
events: SpanEvent[];
```

Defined in: tracing/types.ts:62

Span events (timestamped annotations)

### kind

```ts
kind: SpanKind;
```

Defined in: tracing/types.ts:48

Span kind

### name

```ts
name: string;
```

Defined in: tracing/types.ts:46

Human-readable span name

### parentSpanId?

```ts
optional parentSpanId?: string;
```

Defined in: tracing/types.ts:44

Parent span ID (undefined for root spans)

### spanId

```ts
spanId: string;
```

Defined in: tracing/types.ts:40

Unique span identifier

### startTime

```ts
startTime: number;
```

Defined in: tracing/types.ts:50

Start time in milliseconds since epoch

### status

```ts
status: SpanStatus;
```

Defined in: tracing/types.ts:56

Span status

### statusMessage?

```ts
optional statusMessage?: string;
```

Defined in: tracing/types.ts:58

Status message (typically for errors)

### traceId

```ts
traceId: string;
```

Defined in: tracing/types.ts:42

Trace ID this span belongs to
