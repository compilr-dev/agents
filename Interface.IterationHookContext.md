---
title: "IterationHookContext"
parent: Interfaces
nav_order: 1
---


# Interface: IterationHookContext

Defined in: hooks/types.ts:48

Context for iteration hooks

## Extends

- [`HookContext`](Interface.HookContext.md)

## Properties

### iteration

```ts
iteration: number;
```

Defined in: hooks/types.ts:28

Current iteration number (1-indexed)

#### Inherited from

[`HookContext`](Interface.HookContext.md).[`iteration`](Interface.HookContext.md#iteration)

### maxIterations

```ts
maxIterations: number;
```

Defined in: hooks/types.ts:52

Maximum iterations allowed

### messages

```ts
messages: Message[];
```

Defined in: hooks/types.ts:57

Current message history

### metadata

```ts
metadata: Record<string, unknown>;
```

Defined in: hooks/types.ts:38

Custom metadata that can be passed between hooks

#### Inherited from

[`HookContext`](Interface.HookContext.md).[`metadata`](Interface.HookContext.md#metadata)

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
