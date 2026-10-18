---
title: "routeFor"
parent: Functions
nav_order: 1
---


# Function: routeFor()

```ts
function routeFor(model, baseUrl): OpenAIRoute;
```

Defined in: providers/openai-models.ts:122

Pick the transport for a model id.

The `>= 6` / `5.6` boundary is the whole point: `gpt-7-anything`, `gpt-6.2-nova` and every
future variant route to Responses with NO code change here.

## Parameters

| Parameter | Type |
| ------ | ------ |
| `model` | `string` |
| `baseUrl` | `string` |

## Returns

[`OpenAIRoute`](TypeAlias.OpenAIRoute.md)
