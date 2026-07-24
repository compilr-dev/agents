---
title: "OTelHooksConfig"
parent: Interfaces
nav_order: 1
---


# Interface: OTelHooksConfig

Defined in: tracing/otel-hooks.ts:40

Configuration for OTel hooks

## Properties

### includeIO?

```ts
optional includeIO?: boolean;
```

Defined in: tracing/otel-hooks.ts:54

Include input/output content in span attributes (default: false)

### providerName?

```ts
optional providerName?: string;
```

Defined in: tracing/otel-hooks.ts:46

Provider name for gen_ai.system mapping (e.g. 'claude', 'openai')

### traceIterations?

```ts
optional traceIterations?: boolean;
```

Defined in: tracing/otel-hooks.ts:48

Trace iteration spans (default: true)

### traceLLM?

```ts
optional traceLLM?: boolean;
```

Defined in: tracing/otel-hooks.ts:50

Trace LLM call spans (default: true)

### tracerName?

```ts
optional tracerName?: string;
```

Defined in: tracing/otel-hooks.ts:42

Tracer name (default: '@compilr-dev/agents')

### tracerVersion?

```ts
optional tracerVersion?: string;
```

Defined in: tracing/otel-hooks.ts:44

Tracer version

### traceTools?

```ts
optional traceTools?: boolean;
```

Defined in: tracing/otel-hooks.ts:52

Trace tool execution spans (default: true)

### truncateAt?

```ts
optional truncateAt?: number;
```

Defined in: tracing/otel-hooks.ts:56

Truncate attribute values at this length (default: 1000)
