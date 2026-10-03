---
title: "OpenAIProviderConfig"
parent: Interfaces
nav_order: 1
---


# Interface: OpenAIProviderConfig

Defined in: providers/openai.ts:53

Configuration for OpenAIProvider

## Properties

### apiKey?

```ts
optional apiKey?: string;
```

Defined in: providers/openai.ts:55

OpenAI API key (falls back to OPENAI_API_KEY env var)

### baseUrl?

```ts
optional baseUrl?: string;
```

Defined in: providers/openai.ts:57

Base URL for OpenAI API (default: https://api.openai.com)

### estimateTokens?

```ts
optional estimateTokens?: (text) => number;
```

Defined in: providers/openai.ts:67

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

Defined in: providers/openai.ts:61

Default max tokens (default: 4096)

### model?

```ts
optional model?: string;
```

Defined in: providers/openai.ts:59

Default model to use (default: gpt-4o)

### organization?

```ts
optional organization?: string;
```

Defined in: providers/openai.ts:65

OpenAI organization ID (optional)

### timeout?

```ts
optional timeout?: number;
```

Defined in: providers/openai.ts:63

Request timeout in milliseconds (default: 120000)
