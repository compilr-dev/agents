---
title: "clampEffort"
parent: Functions
nav_order: 1
---


# Function: clampEffort()

```ts
function clampEffort(model, effort): OpenAIEffort;
```

Defined in: providers/openai-models.ts:167

Bring an effort level into the set a model accepts: prefer the nearest weaker level, else the
nearest stronger one. `xhigh` on a model that does not list it becomes `high`; `none` on Astra
becomes `low`.

## Parameters

| Parameter | Type |
| ------ | ------ |
| `model` | `string` |
| `effort` | [`OpenAIEffort`](TypeAlias.OpenAIEffort.md) |

## Returns

[`OpenAIEffort`](TypeAlias.OpenAIEffort.md)
