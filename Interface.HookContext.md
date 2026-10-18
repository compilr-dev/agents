---
title: "HookContext"
parent: Interfaces
nav_order: 1
---


# Interface: HookContext

Defined in: hooks/types.ts:19

Context available in all hook calls

## Extended by

- [`IterationHookContext`](Interface.IterationHookContext.md)
- [`LLMHookContext`](Interface.LLMHookContext.md)
- [`ToolHookContext`](Interface.ToolHookContext.md)
- [`ErrorHookContext`](Interface.ErrorHookContext.md)

## Properties

### iteration

```ts
iteration: number;
```

Defined in: hooks/types.ts:28

Current iteration number (1-indexed)

### metadata

```ts
metadata: Record<string, unknown>;
```

Defined in: hooks/types.ts:38

Custom metadata that can be passed between hooks

### sessionId

```ts
sessionId: string;
```

Defined in: hooks/types.ts:23

Current session ID

### signal?

```ts
optional signal?: AbortSignal;
```

Defined in: hooks/types.ts:33

Abort signal for cancellation
