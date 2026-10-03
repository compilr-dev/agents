---
title: "estimateEffort"
parent: Functions
nav_order: 1
---


# Function: estimateEffort()

```ts
function estimateEffort(signals, weights?): Effort;
```

Defined in: episodes/effort.ts:68

Estimate effort level from raw signals.

Score formula:
  fileCount * fileCountMultiplier
  + min(linesChanged / linesPerPoint, 10)
  + toolCallCount * toolCallWeight
  + (durationMs / 60000) / minutesPerPoint
  + complexity bonuses: newFiles(+5), multiLang(+3), tests(+5), config(+2)

Thresholds:
  < 5 = trivial, < 15 = low, < 40 = medium, < 100 = high, else = significant

## Parameters

| Parameter | Type |
| ------ | ------ |
| `signals` | [`EffortSignals`](Interface.EffortSignals.md) |
| `weights?` | `Partial`\<[`EffortWeights`](Interface.EffortWeights.md)\> |

## Returns

[`Effort`](TypeAlias.Effort.md)
