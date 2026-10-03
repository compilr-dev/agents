---
title: "parseOpenAIModel"
parent: Functions
nav_order: 1
---


# Function: parseOpenAIModel()

```ts
function parseOpenAIModel(model): ParsedOpenAIModel | null;
```

Defined in: providers/openai-models.ts:41

`gpt-6-astra` → `{6, 0, 'astra'}`; `gpt-5.6-sol` → `{5, 6, 'sol'}`;
`gpt-5.2-2025-12-11` → `{5, 2}`; `gpt-5-mini-2025-08-07` → `{5, 0, 'mini'}`;
`gpt-4o` → `{4, 0}`; `gpt-4o-mini` → `{4, 0, 'mini'}`.

Returns `null` for anything that is not a `gpt-<n>` id (`o1-preview`, a proxy alias,
`openai/gpt-6-sol`). Callers must treat `null` as "assume the old behaviour".

## Parameters

| Parameter | Type |
| ------ | ------ |
| `model` | `string` |

## Returns

[`ParsedOpenAIModel`](Interface.ParsedOpenAIModel.md) \| `null`
