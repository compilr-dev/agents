---
title: "CompactionConfig"
parent: Interfaces
nav_order: 1
---


# Interface: CompactionConfig

Defined in: context/types.ts:233

Compaction configuration - replaces old content with file references

## Properties

### minTokensToCompact

```ts
minTokensToCompact: number;
```

Defined in: context/types.ts:256

Minimum tokens in a message to consider for compaction

#### Default

```ts
1000
```

### preserveRecentTurns

```ts
preserveRecentTurns: number;
```

Defined in: context/types.ts:250

Number of recent turns to preserve (not compact)

#### Default

```ts
10
```

### triggerInterval

```ts
triggerInterval: number;
```

Defined in: context/types.ts:238

Trigger compaction every N turns

#### Default

```ts
20
```

### triggerThreshold

```ts
triggerThreshold: number;
```

Defined in: context/types.ts:244

Trigger compaction when context utilization exceeds this threshold

#### Default

```ts
0.5 (50%)
```
