---
title: "SpanEvent"
parent: Interfaces
nav_order: 1
---


# Interface: SpanEvent

Defined in: tracing/types.ts:68

Event within a span (timestamped annotation)

## Properties

### attributes?

```ts
optional attributes?: SpanAttributes;
```

Defined in: tracing/types.ts:74

Event attributes

### name

```ts
name: string;
```

Defined in: tracing/types.ts:70

Event name

### timestamp

```ts
timestamp: number;
```

Defined in: tracing/types.ts:72

Timestamp in milliseconds since epoch
