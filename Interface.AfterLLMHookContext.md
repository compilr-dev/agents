---
title: "AfterLLMHookContext"
parent: Interfaces
nav_order: 1
---


# Interface: AfterLLMHookContext

Defined in: hooks/types.ts:164

Context for after:llm hook

## Extends

- [`LLMHookContext`](Interface.LLMHookContext.md)

## Properties

### durationMs

```ts
durationMs: number;
```

Defined in: hooks/types.ts:195

Duration of the LLM call in milliseconds

### iteration

```ts
iteration: number;
```

Defined in: hooks/types.ts:28

Current iteration number (1-indexed)

#### Inherited from

[`LLMHookContext`](Interface.LLMHookContext.md).[`iteration`](Interface.LLMHookContext.md#iteration)

### messages

```ts
messages: Message[];
```

Defined in: hooks/types.ts:111

Messages to be sent to LLM

#### Inherited from

[`LLMHookContext`](Interface.LLMHookContext.md).[`messages`](Interface.LLMHookContext.md#messages)

### metadata

```ts
metadata: Record<string, unknown>;
```

Defined in: hooks/types.ts:38

Custom metadata that can be passed between hooks

#### Inherited from

[`LLMHookContext`](Interface.LLMHookContext.md).[`metadata`](Interface.LLMHookContext.md#metadata)

### model?

```ts
optional model?: string;
```

Defined in: hooks/types.ts:190

Model that was used

### sessionId

```ts
sessionId: string;
```

Defined in: hooks/types.ts:23

Current session ID

#### Inherited from

[`LLMHookContext`](Interface.LLMHookContext.md).[`sessionId`](Interface.LLMHookContext.md#sessionid)

### signal?

```ts
optional signal?: AbortSignal;
```

Defined in: hooks/types.ts:33

Abort signal for cancellation

#### Inherited from

[`LLMHookContext`](Interface.LLMHookContext.md).[`signal`](Interface.LLMHookContext.md#signal)

### systemPrompt

```ts
systemPrompt: string;
```

Defined in: hooks/types.ts:122

Current system prompt (fully assembled, including anchors).
Hooks can read this and return a modified version in BeforeLLMHookResult.

#### Inherited from

[`LLMHookContext`](Interface.LLMHookContext.md).[`systemPrompt`](Interface.LLMHookContext.md#systemprompt)

### text

```ts
text: string;
```

Defined in: hooks/types.ts:168

Text response from LLM

### tools

```ts
tools: ToolDefinition[];
```

Defined in: hooks/types.ts:116

Tool definitions available to LLM

#### Inherited from

[`LLMHookContext`](Interface.LLMHookContext.md).[`tools`](Interface.LLMHookContext.md#tools)

### toolUses

```ts
toolUses: {
  id: string;
  input: Record<string, unknown>;
  name: string;
}[];
```

Defined in: hooks/types.ts:173

Tool uses requested by LLM

#### id

```ts
id: string;
```

#### input

```ts
input: Record<string, unknown>;
```

#### name

```ts
name: string;
```

### usage?

```ts
optional usage?: {
  inputTokens: number;
  outputTokens: number;
};
```

Defined in: hooks/types.ts:182

Token usage from the call

#### inputTokens

```ts
inputTokens: number;
```

#### outputTokens

```ts
outputTokens: number;
```
