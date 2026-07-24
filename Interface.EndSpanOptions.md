---
title: "EndSpanOptions"
parent: Interfaces
nav_order: 1
---


# Interface: EndSpanOptions

Defined in: tracing/types.ts:193

Options for ending a span

## Properties

### attributes?

```ts
optional attributes?: SpanAttributes;
```

Defined in: tracing/types.ts:201

Additional attributes to add

### endTime?

```ts
optional endTime?: number;
```

Defined in: tracing/types.ts:195

End time override (default: now)

### status?

```ts
optional status?: SpanStatus;
```

Defined in: tracing/types.ts:197

Final status

### statusMessage?

```ts
optional statusMessage?: string;
```

Defined in: tracing/types.ts:199

Status message
