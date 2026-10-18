---
title: "PerplexityProviderConfig"
parent: Interfaces
nav_order: 1
---


# Interface: PerplexityProviderConfig

Defined in: providers/perplexity.ts:32

Configuration for PerplexityProvider

## Properties

### apiKey?

```ts
optional apiKey?: string;
```

Defined in: providers/perplexity.ts:34

Perplexity API key (falls back to PERPLEXITY_API_KEY env var)

### baseUrl?

```ts
optional baseUrl?: string;
```

Defined in: providers/perplexity.ts:36

Base URL for Perplexity API (default: https://api.perplexity.ai)

### estimateTokens?

```ts
optional estimateTokens?: (text) => number;
```

Defined in: providers/perplexity.ts:44

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

Defined in: providers/perplexity.ts:40

Default max tokens (default: 4096)

### model?

```ts
optional model?: string;
```

Defined in: providers/perplexity.ts:38

Default model to use (default: sonar)

### timeout?

```ts
optional timeout?: number;
```

Defined in: providers/perplexity.ts:42

Request timeout in milliseconds (default: 120000)
