---
title: "OpenAICompatibleConfig"
parent: Interfaces
nav_order: 1
---


# Interface: OpenAICompatibleConfig

Defined in: providers/openai-compatible.ts:114

Base configuration for OpenAI-compatible providers

## Properties

### baseUrl

```ts
baseUrl: string;
```

Defined in: providers/openai-compatible.ts:116

Base URL for the API

### estimateTokens?

```ts
optional estimateTokens?: (text) => number;
```

Defined in: providers/openai-compatible.ts:128

Optional token estimator function (e.g., tiktoken).
When provided, debug payload reports token counts instead of char-based estimates.
Fallback: Math.ceil(text.length / 4)

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `text` | `string` |

#### Returns

`number`

### maxTokens?

```ts
optional maxTokens?: number;
```

Defined in: providers/openai-compatible.ts:120

Default max tokens (default: 4096)

### model

```ts
model: string;
```

Defined in: providers/openai-compatible.ts:118

Default model to use

### timeout?

```ts
optional timeout?: number;
```

Defined in: providers/openai-compatible.ts:122

Request timeout in milliseconds (default: 120000)
