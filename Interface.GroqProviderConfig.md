---
title: "GroqProviderConfig"
parent: Interfaces
nav_order: 1
---


# Interface: GroqProviderConfig

Defined in: providers/groq.ts:32

Configuration for GroqProvider

## Properties

### apiKey?

```ts
optional apiKey?: string;
```

Defined in: providers/groq.ts:34

Groq API key (falls back to GROQ_API_KEY env var)

### baseUrl?

```ts
optional baseUrl?: string;
```

Defined in: providers/groq.ts:36

Base URL for Groq API (default: https://api.groq.com/openai)

### estimateTokens?

```ts
optional estimateTokens?: (text) => number;
```

Defined in: providers/groq.ts:44

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

Defined in: providers/groq.ts:40

Default max tokens (default: 4096)

### model?

```ts
optional model?: string;
```

Defined in: providers/groq.ts:38

Default model to use (default: llama-3.2-8b-preview)

### timeout?

```ts
optional timeout?: number;
```

Defined in: providers/groq.ts:42

Request timeout in milliseconds (default: 120000)
