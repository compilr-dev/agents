---
title: "AfterToolHookContext"
parent: Interfaces
nav_order: 1
---


# Interface: AfterToolHookContext

Defined in: hooks/types.ts:266

Context for after:tool hook

## Extends

- [`ToolHookContext`](Interface.ToolHookContext.md)

## Properties

### durationMs

```ts
durationMs: number;
```

Defined in: hooks/types.ts:275

Duration of tool execution in milliseconds

### input

```ts
input: Record<string, unknown>;
```

Defined in: hooks/types.ts:225

Input arguments for the tool

#### Inherited from

[`ToolHookContext`](Interface.ToolHookContext.md).[`input`](Interface.ToolHookContext.md#input)

### iteration

```ts
iteration: number;
```

Defined in: hooks/types.ts:28

Current iteration number (1-indexed)

#### Inherited from

[`ToolHookContext`](Interface.ToolHookContext.md).[`iteration`](Interface.ToolHookContext.md#iteration)

### metadata

```ts
metadata: Record<string, unknown>;
```

Defined in: hooks/types.ts:38

Custom metadata that can be passed between hooks

#### Inherited from

[`ToolHookContext`](Interface.ToolHookContext.md).[`metadata`](Interface.ToolHookContext.md#metadata)

### result

```ts
result: ToolExecutionResult;
```

Defined in: hooks/types.ts:270

Result from tool execution

### sessionId

```ts
sessionId: string;
```

Defined in: hooks/types.ts:23

Current session ID

#### Inherited from

[`ToolHookContext`](Interface.ToolHookContext.md).[`sessionId`](Interface.ToolHookContext.md#sessionid)

### signal?

```ts
optional signal?: AbortSignal;
```

Defined in: hooks/types.ts:33

Abort signal for cancellation

#### Inherited from

[`ToolHookContext`](Interface.ToolHookContext.md).[`signal`](Interface.ToolHookContext.md#signal)

### toolName

```ts
toolName: string;
```

Defined in: hooks/types.ts:220

Name of the tool being executed

#### Inherited from

[`ToolHookContext`](Interface.ToolHookContext.md).[`toolName`](Interface.ToolHookContext.md#toolname)
