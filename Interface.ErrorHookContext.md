---
title: "ErrorHookContext"
parent: Interfaces
nav_order: 1
---


# Interface: ErrorHookContext

Defined in: hooks/types.ts:308

Context for error hooks

## Extends

- [`HookContext`](Interface.HookContext.md)

## Properties

### error

```ts
error: Error;
```

Defined in: hooks/types.ts:312

The error that occurred

### iteration

```ts
iteration: number;
```

Defined in: hooks/types.ts:28

Current iteration number (1-indexed)

#### Inherited from

[`HookContext`](Interface.HookContext.md).[`iteration`](Interface.HookContext.md#iteration)

### metadata

```ts
metadata: Record<string, unknown>;
```

Defined in: hooks/types.ts:38

Custom metadata that can be passed between hooks

#### Inherited from

[`HookContext`](Interface.HookContext.md).[`metadata`](Interface.HookContext.md#metadata)

### phase

```ts
phase: "llm" | "tool" | "iteration";
```

Defined in: hooks/types.ts:317

Phase where the error occurred

### sessionId

```ts
sessionId: string;
```

Defined in: hooks/types.ts:23

Current session ID

#### Inherited from

[`HookContext`](Interface.HookContext.md).[`sessionId`](Interface.HookContext.md#sessionid)

### signal?

```ts
optional signal?: AbortSignal;
```

Defined in: hooks/types.ts:33

Abort signal for cancellation

#### Inherited from

[`HookContext`](Interface.HookContext.md).[`signal`](Interface.HookContext.md#signal)

### toolName?

```ts
optional toolName?: string;
```

Defined in: hooks/types.ts:322

Tool name (if error occurred during tool execution)
