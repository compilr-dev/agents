---
title: "Trace"
parent: Interfaces
nav_order: 1
---


# Interface: Trace

Defined in: tracing/types.ts:94

A complete trace containing multiple spans

## Properties

### attributes

```ts
attributes: SpanAttributes;
```

Defined in: tracing/types.ts:108

Trace-level attributes

### durationMs?

```ts
optional durationMs?: number;
```

Defined in: tracing/types.ts:106

Total duration in milliseconds

### endTime?

```ts
optional endTime?: number;
```

Defined in: tracing/types.ts:104

Trace end time (undefined if still active)

### rootSpanId

```ts
rootSpanId: string;
```

Defined in: tracing/types.ts:98

Root span ID

### spans

```ts
spans: Span[];
```

Defined in: tracing/types.ts:100

All spans in this trace

### startTime

```ts
startTime: number;
```

Defined in: tracing/types.ts:102

Trace start time

### traceId

```ts
traceId: string;
```

Defined in: tracing/types.ts:96

Unique trace identifier
