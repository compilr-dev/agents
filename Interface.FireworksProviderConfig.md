---
title: "FireworksProviderConfig"
parent: Interfaces
nav_order: 1
---


# Interface: FireworksProviderConfig

Defined in: providers/fireworks.ts:32

Configuration for FireworksProvider

## Properties

### apiKey?

```ts
optional apiKey?: string;
```

Defined in: providers/fireworks.ts:34

Fireworks AI API key (falls back to FIREWORKS_API_KEY env var)

### baseUrl?

```ts
optional baseUrl?: string;
```

Defined in: providers/fireworks.ts:36

Base URL for Fireworks API (default: https://api.fireworks.ai/inference)

### estimateTokens?

```ts
optional estimateTokens?: (text) => number;
```

Defined in: providers/fireworks.ts:44

Optional token estimator (e.g., tiktoken) for debug payload

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

Defined in: providers/fireworks.ts:40

Default max tokens (default: 4096)

### model?

```ts
optional model?: string;
```

Defined in: providers/fireworks.ts:38

Default model to use (default: accounts/fireworks/models/llama-v3p1-8b-instruct)

### timeout?

```ts
optional timeout?: number;
```

Defined in: providers/fireworks.ts:42

Request timeout in milliseconds (default: 120000)
