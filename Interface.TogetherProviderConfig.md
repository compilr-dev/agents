---
title: "TogetherProviderConfig"
parent: Interfaces
nav_order: 1
---


# Interface: TogetherProviderConfig

Defined in: providers/together.ts:32

Configuration for TogetherProvider

## Properties

### apiKey?

```ts
optional apiKey?: string;
```

Defined in: providers/together.ts:34

Together AI API key (falls back to TOGETHER_API_KEY env var)

### baseUrl?

```ts
optional baseUrl?: string;
```

Defined in: providers/together.ts:36

Base URL for Together API (default: https://api.together.xyz)

### estimateTokens?

```ts
optional estimateTokens?: (text) => number;
```

Defined in: providers/together.ts:44

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

Defined in: providers/together.ts:40

Default max tokens (default: 4096)

### model?

```ts
optional model?: string;
```

Defined in: providers/together.ts:38

Default model to use (default: meta-llama/Meta-Llama-3.1-8B-Instruct-Turbo)

### timeout?

```ts
optional timeout?: number;
```

Defined in: providers/together.ts:42

Request timeout in milliseconds (default: 120000)
