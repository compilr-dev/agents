---
title: "createOpenAIResponsesProvider"
parent: Functions
nav_order: 1
---


# Function: createOpenAIResponsesProvider()

```ts
function createOpenAIResponsesProvider(config?): OpenAIResponsesProvider;
```

Defined in: providers/openai-responses.ts:907

Create an OpenAI Responses-API provider.

Most callers want [createOpenAIProvider](Function.createOpenAIProvider.md) instead, which routes to this transport
automatically for the models that require it.

## Parameters

| Parameter | Type |
| ------ | ------ |
| `config` | [`OpenAIResponsesProviderConfig`](Interface.OpenAIResponsesProviderConfig.md) |

## Returns

[`OpenAIResponsesProvider`](Class.OpenAIResponsesProvider.md)
