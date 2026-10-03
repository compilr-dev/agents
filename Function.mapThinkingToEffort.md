---
title: "mapThinkingToEffort"
parent: Functions
nav_order: 1
---


# Function: mapThinkingToEffort()

```ts
function mapThinkingToEffort(thinking, model): OpenAIEffort | undefined;
```

Defined in: providers/openai-models.ts:191

Our `ThinkingConfig` → the `reasoning.effort` we send. `undefined` means **omit `reasoning`
entirely** and let the model use its own default; tools work at any effort on this endpoint.

⚠️ `'none'` is NEVER returned, and that is deliberate rather than tidy. `'none'` is the one
value measured to be *rejected* (Astra, 400); `'low'` is measured to work on all three GPT-6
models. Mapping `disabled → 'low'` means the string `'none'` cannot leave this process, so the
single per-model exception we know about can never fire and `allowedEfforts()` never has to be
right for us to be correct. The cost is honest and small: a caller asking for reasoning off
gets minimal reasoning instead.

## Parameters

| Parameter | Type |
| ------ | ------ |
| `thinking` | `ThinkingConfig` \| `undefined` |
| `model` | `string` |

## Returns

[`OpenAIEffort`](TypeAlias.OpenAIEffort.md) \| `undefined`
