---
title: "ToolHookContext"
parent: Interfaces
nav_order: 1
---


# Interface: ToolHookContext

Defined in: hooks/types.ts:216

Context for tool hooks

## Extends

- [`HookContext`](Interface.HookContext.md)

## Extended by

- [`AfterToolHookContext`](Interface.AfterToolHookContext.md)

## Properties

### input

```ts
input: Record<string, unknown>;
```

Defined in: hooks/types.ts:225

Input arguments for the tool

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

### toolName

```ts
toolName: string;
```

Defined in: hooks/types.ts:220

Name of the tool being executed
