---
title: "OpenRouterProviderConfig"
parent: Interfaces
nav_order: 1
---


# Interface: OpenRouterProviderConfig

Defined in: providers/openrouter.ts:33

Configuration for OpenRouterProvider

## Properties

### apiKey?

```ts
optional apiKey?: string;
```

Defined in: providers/openrouter.ts:35

OpenRouter API key (falls back to OPENROUTER_API_KEY env var)

### baseUrl?

```ts
optional baseUrl?: string;
```

Defined in: providers/openrouter.ts:37

Base URL for OpenRouter API (default: https://openrouter.ai/api)

### estimateTokens?

```ts
optional estimateTokens?: (text) => number;
```

Defined in: providers/openrouter.ts:49

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

Defined in: providers/openrouter.ts:41

Default max tokens (default: 4096)

### model?

```ts
optional model?: string;
```

Defined in: providers/openrouter.ts:39

Default model to use (default: meta-llama/llama-3.1-8b-instruct)

### siteName?

```ts
optional siteName?: string;
```

Defined in: providers/openrouter.ts:47

Site name for OpenRouter rankings (optional)

### siteUrl?

```ts
optional siteUrl?: string;
```

Defined in: providers/openrouter.ts:45

Site URL for OpenRouter rankings (optional)

### timeout?

```ts
optional timeout?: number;
```

Defined in: providers/openrouter.ts:43

Request timeout in milliseconds (default: 120000)
