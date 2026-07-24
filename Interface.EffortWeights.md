---
title: "EffortWeights"
parent: Interfaces
nav_order: 1
---


# Interface: EffortWeights

Defined in: episodes/types.ts:115

Tunable weights for effort estimation.
All weights are multipliers or divisors applied to raw signals.

## Properties

### fileCountMultiplier

```ts
fileCountMultiplier: number;
```

Defined in: episodes/types.ts:117

Points per file (default: 2)

### linesPerPoint

```ts
linesPerPoint: number;
```

Defined in: episodes/types.ts:120

Lines per point (default: 50) — higher means lines matter less

### minutesPerPoint

```ts
minutesPerPoint: number;
```

Defined in: episodes/types.ts:123

Minutes per point (default: 1)

### toolCallWeight

```ts
toolCallWeight: number;
```

Defined in: episodes/types.ts:126

Points per tool call (default: 1)
