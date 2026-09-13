---
title: "UsageStats"
parent: Interfaces
nav_order: 1
---


# Interface: UsageStats

Defined in: costs/types.ts:48

Aggregated usage statistics

## Properties

### averageTokensPerCall

```ts
averageTokensPerCall: number;
```

Defined in: costs/types.ts:62

Average tokens per call

### byModel

```ts
byModel: Record<string, {
  calls: number;
  inputTokens: number;
  outputTokens: number;
  totalTokens: number;
}>;
```

Defined in: costs/types.ts:68

Usage by model

### firstCall?

```ts
optional firstCall?: Date;
```

Defined in: costs/types.ts:64

First call timestamp

### lastCall?

```ts
optional lastCall?: Date;
```

Defined in: costs/types.ts:66

Last call timestamp

### totalCacheCreationTokens

```ts
totalCacheCreationTokens: number;
```

Defined in: costs/types.ts:60

Total cache creation tokens

### totalCacheReadTokens

```ts
totalCacheReadTokens: number;
```

Defined in: costs/types.ts:58

Total cache read tokens

### totalCalls

```ts
totalCalls: number;
```

Defined in: costs/types.ts:50

Total number of LLM calls

### totalInputTokens

```ts
totalInputTokens: number;
```

Defined in: costs/types.ts:52

Total input tokens

### totalOutputTokens

```ts
totalOutputTokens: number;
```

Defined in: costs/types.ts:54

Total output tokens

### totalTokens

```ts
totalTokens: number;
```

Defined in: costs/types.ts:56

Total tokens
