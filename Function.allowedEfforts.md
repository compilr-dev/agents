---
title: "allowedEfforts"
parent: Functions
nav_order: 1
---


# Function: allowedEfforts()

```ts
function allowedEfforts(model): readonly OpenAIEffort[];
```

Defined in: providers/openai-models.ts:155

Effort levels a model offers.

⚠️ NOT load-bearing. `mapThinkingToEffort()` already guarantees the string `'none'` never
leaves this process, so a wrong entry here cannot produce a 400. This exists to tell a UI
which levels to show, and to give `clampEffort()` something to clamp against.

## Parameters

| Parameter | Type |
| ------ | ------ |
| `model` | `string` |

## Returns

readonly [`OpenAIEffort`](TypeAlias.OpenAIEffort.md)[]
