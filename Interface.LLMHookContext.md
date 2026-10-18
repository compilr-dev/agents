---
title: "LLMHookContext"
parent: Interfaces
nav_order: 1
---


# Interface: LLMHookContext

Defined in: hooks/types.ts:107

Context for LLM hooks

## Extends

- [`HookContext`](Interface.HookContext.md)

## Extended by

- [`AfterLLMHookContext`](Interface.AfterLLMHookContext.md)

## Properties

### iteration

```ts
iteration: number;
```

Defined in: hooks/types.ts:28

Current iteration number (1-indexed)

#### Inherited from

[`HookContext`](Interface.HookContext.md).[`iteration`](Interface.HookContext.md#iteration)

### messages

```ts
messages: Message[];
```

Defined in: hooks/types.ts:111

Messages to be sent to LLM

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

### systemPrompt

```ts
systemPrompt: string;
```

Defined in: hooks/types.ts:122

Current system prompt (fully assembled, including anchors).
Hooks can read this and return a modified version in BeforeLLMHookResult.

### tools

```ts
tools: ToolDefinition[];
```

Defined in: hooks/types.ts:116

Tool definitions available to LLM
