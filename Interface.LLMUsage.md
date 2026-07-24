---
title: "LLMUsage"
parent: Interfaces
nav_order: 1
---


# Interface: LLMUsage

Defined in: providers/types.ts:94

Token usage from an LLM response (returned on 'done' chunks)

## Properties

### cacheCreationTokens?

```ts
optional cacheCreationTokens?: number;
```

Defined in: providers/types.ts:98

### cacheReadTokens?

```ts
optional cacheReadTokens?: number;
```

Defined in: providers/types.ts:97

### debugPayload?

```ts
optional debugPayload?: {
  contentsTokens: number;
  systemTokens: number;
  toolsTokens: number;
};
```

Defined in: providers/types.ts:102

Debug payload info - estimated token counts before sending to provider

#### contentsTokens

```ts
contentsTokens: number;
```

#### systemTokens

```ts
systemTokens: number;
```

#### toolsTokens

```ts
toolsTokens: number;
```

### inputTokens

```ts
inputTokens: number;
```

Defined in: providers/types.ts:95

### outputTokens

```ts
outputTokens: number;
```

Defined in: providers/types.ts:96

### thinkingTokens?

```ts
optional thinkingTokens?: number;
```

Defined in: providers/types.ts:100

Thinking tokens (Gemini 2.5+ models with thinking)
