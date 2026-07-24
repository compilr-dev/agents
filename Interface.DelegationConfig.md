---
title: "DelegationConfig"
parent: Interfaces
nav_order: 1
---


# Interface: DelegationConfig

Defined in: context/delegation-types.ts:13

Configuration for tool result delegation.
Controls when and how large tool results are summarized.

## Properties

### delegationThreshold

```ts
delegationThreshold: number;
```

Defined in: context/delegation-types.ts:18

Token count above which results are delegated. Default: 8000

### enabled

```ts
enabled: boolean;
```

Defined in: context/delegation-types.ts:15

Whether delegation is enabled. Default: false (opt-in)

### maxStoredResults

```ts
maxStoredResults: number;
```

Defined in: context/delegation-types.ts:27

Maximum number of stored results (LRU eviction). Default: 50

### resultTTL

```ts
resultTTL: number;
```

Defined in: context/delegation-types.ts:24

Milliseconds before stored results expire. Default: 600_000 (10 min)

### strategy

```ts
strategy: "llm" | "extractive" | "auto";
```

Defined in: context/delegation-types.ts:30

Summarization strategy. Default: 'auto'

### summaryMaxTokens

```ts
summaryMaxTokens: number;
```

Defined in: context/delegation-types.ts:21

Maximum tokens for the summary. Default: 800

### toolOverrides?

```ts
optional toolOverrides?: Record<string, {
  enabled?: boolean;
  strategy?: "llm" | "extractive" | "auto";
  threshold?: number;
}>;
```

Defined in: context/delegation-types.ts:33

Per-tool threshold/strategy overrides
