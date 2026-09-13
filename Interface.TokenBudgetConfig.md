---
title: "TokenBudgetConfig"
parent: Interfaces
nav_order: 1
---


# Interface: TokenBudgetConfig

Defined in: costs/types.ts:82

Token budget configuration

## Properties

### maxInputTokens?

```ts
optional maxInputTokens?: number;
```

Defined in: costs/types.ts:86

Maximum input tokens allowed

### maxOutputTokens?

```ts
optional maxOutputTokens?: number;
```

Defined in: costs/types.ts:88

Maximum output tokens allowed

### maxTokensPerSession?

```ts
optional maxTokensPerSession?: number;
```

Defined in: costs/types.ts:90

Maximum tokens per session

### maxTotalTokens?

```ts
optional maxTotalTokens?: number;
```

Defined in: costs/types.ts:84

Maximum total tokens allowed

### warningThreshold?

```ts
optional warningThreshold?: number;
```

Defined in: costs/types.ts:92

Warning threshold (0-1, triggers warning event when utilization reaches this)
