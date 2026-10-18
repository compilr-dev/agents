---
title: "ContextConfig"
parent: Interfaces
nav_order: 1
---


# Interface: ContextConfig

Defined in: context/types.ts:171

Context management configuration

## Properties

### budget

```ts
budget: BudgetAllocation;
```

Defined in: context/types.ts:182

Budget allocation for each category
Enables category-specific compaction

### compaction

```ts
compaction: CompactionConfig;
```

Defined in: context/types.ts:198

Compaction configuration

### filtering

```ts
filtering: FilteringConfig;
```

Defined in: context/types.ts:193

Filtering configuration

### maxContextTokens

```ts
maxContextTokens: number;
```

Defined in: context/types.ts:176

Maximum tokens for the context window

#### Default

```ts
200000 (Claude's limit)
```

### summarization

```ts
summarization: SummarizationConfig;
```

Defined in: context/types.ts:203

Summarization configuration

### verbosity

```ts
verbosity: VerbosityConfig;
```

Defined in: context/types.ts:188

Verbosity level thresholds
Controls graceful degradation
