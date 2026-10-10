---
title: "TokenUsage"
parent: Interfaces
nav_order: 1
---


# Interface: TokenUsage

Defined in: costs/types.ts:12

Token usage for a single LLM call

## Properties

### cacheCreationTokens?

```ts
optional cacheCreationTokens?: number;
```

Defined in: costs/types.ts:22

Cache creation tokens (if applicable)

### cacheReadTokens?

```ts
optional cacheReadTokens?: number;
```

Defined in: costs/types.ts:20

Cache read tokens (if applicable)

### inputTokens

```ts
inputTokens: number;
```

Defined in: costs/types.ts:14

Input/prompt tokens

### outputTokens

```ts
outputTokens: number;
```

Defined in: costs/types.ts:16

Output/completion tokens

### totalTokens

```ts
totalTokens: number;
```

Defined in: costs/types.ts:18

Total tokens (input + output)
