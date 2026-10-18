---
title: "BeforeLLMHookResult"
parent: Interfaces
nav_order: 1
---


# Interface: BeforeLLMHookResult

Defined in: hooks/types.ts:128

Result from before:llm hook that modifies messages or tools

## Properties

### messages?

```ts
optional messages?: Message[];
```

Defined in: hooks/types.ts:132

Modified messages (optional, original used if not provided)

### systemPrompt?

```ts
optional systemPrompt?: string;
```

Defined in: hooks/types.ts:143

Modified system prompt (optional, original used if not provided).
When returned, messages[0] (system message) is updated automatically.

### tools?

```ts
optional tools?: ToolDefinition[];
```

Defined in: hooks/types.ts:137

Modified tools (optional, original used if not provided)
