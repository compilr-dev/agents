---
title: "TracingHooksConfig"
parent: Interfaces
nav_order: 1
---


# Interface: TracingHooksConfig

Defined in: tracing/types.ts:336

Configuration for built-in tracing hooks

## Properties

### attributeMapper?

```ts
optional attributeMapper?: (phase, data) => SpanAttributes;
```

Defined in: tracing/types.ts:348

Custom attribute mapper

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `phase` | `"llm"` \| `"tool"` \| `"iteration"` |
| `data` | `Record`\<`string`, `unknown`\> |

#### Returns

[`SpanAttributes`](TypeAlias.SpanAttributes.md)

### includeIO?

```ts
optional includeIO?: boolean;
```

Defined in: tracing/types.ts:344

Include input/output in attributes (may be verbose)

### traceIterations?

```ts
optional traceIterations?: boolean;
```

Defined in: tracing/types.ts:342

Trace iterations

### traceLLM?

```ts
optional traceLLM?: boolean;
```

Defined in: tracing/types.ts:338

Trace LLM calls

### traceTools?

```ts
optional traceTools?: boolean;
```

Defined in: tracing/types.ts:340

Trace tool executions

### truncateAt?

```ts
optional truncateAt?: number;
```

Defined in: tracing/types.ts:346

Truncate long values at this length
