---
title: "TracingHookContext"
parent: Interfaces
nav_order: 1
---


# Interface: TracingHookContext

Defined in: tracing/types.ts:357

Context passed to tracing hooks

## Properties

### manager

```ts
manager: TracingManagerInterface;
```

Defined in: tracing/types.ts:359

Tracing manager instance

### sessionId

```ts
sessionId: string;
```

Defined in: tracing/types.ts:365

Session ID

### spanContext?

```ts
optional spanContext?: SpanContext;
```

Defined in: tracing/types.ts:363

Current span context

### traceId

```ts
traceId: string;
```

Defined in: tracing/types.ts:361

Current trace ID
