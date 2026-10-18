---
title: "Tool"
parent: Interfaces
nav_order: 1
---


# Interface: Tool\<T\>

Defined in: tools/types.ts:135

## Type Parameters

| Type Parameter | Default type |
| ------ | ------ |
| `T` | `object` |

## Properties

### definition

```ts
definition: ToolDefinition;
```

Defined in: tools/types.ts:136

### execute

```ts
execute: ToolHandler<T>;
```

Defined in: tools/types.ts:137

### parallel?

```ts
optional parallel?: boolean;
```

Defined in: tools/types.ts:144

If true, multiple calls to this tool can execute in parallel.
When the LLM requests multiple parallel-safe tools in one response,
they will be executed concurrently using Promise.all.
Default: false (sequential execution)

### readonly?

```ts
optional readonly?: boolean;
```

Defined in: tools/types.ts:157

If true, this tool performs no side effects (only reads data).
Read-only tools are automatically batched for parallel execution
even in a mixed batch with write tools.
Default: false

### repeatable?

```ts
optional repeatable?: boolean;
```

Defined in: tools/types.ts:164

If true, this tool is exempt from tool-loop detection — repeated identical
calls are always legitimate (e.g. genuinely idempotent pollers). Most
polling tools do NOT need this: loop detection is result-aware, so calls
that return changing output don't trip. Default: false.

### silent?

```ts
optional silent?: boolean;
```

Defined in: tools/types.ts:150

If true, this tool runs silently without spinner updates or result output.
Used for internal housekeeping tools like todo_read, suggest, etc.
Default: false (normal visibility)
