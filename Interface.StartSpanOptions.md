---
title: "StartSpanOptions"
parent: Interfaces
nav_order: 1
---


# Interface: StartSpanOptions

Defined in: tracing/types.ts:177

Options for starting a span

## Properties

### attributes?

```ts
optional attributes?: SpanAttributes;
```

Defined in: tracing/types.ts:185

Initial attributes

### kind?

```ts
optional kind?: SpanKind;
```

Defined in: tracing/types.ts:181

Span kind (default: internal)

### name

```ts
name: string;
```

Defined in: tracing/types.ts:179

Span name

### parentContext?

```ts
optional parentContext?: SpanContext;
```

Defined in: tracing/types.ts:183

Parent span context (if not provided, uses current context)

### startTime?

```ts
optional startTime?: number;
```

Defined in: tracing/types.ts:187

Start time override (default: now)
