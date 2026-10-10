---
title: "OpenAIResponsesProviderConfig"
parent: Interfaces
nav_order: 1
---


# Interface: OpenAIResponsesProviderConfig

Defined in: providers/openai-responses.ts:134

Configuration for [OpenAIResponsesProvider](Class.OpenAIResponsesProvider.md).

Field names and defaults mirror `OpenAIProviderConfig` exactly, so the router can forward its
own config untouched.

## Properties

### apiKey?

```ts
optional apiKey?: string;
```

Defined in: providers/openai-responses.ts:136

OpenAI API key (falls back to OPENAI_API_KEY env var)

### baseUrl?

```ts
optional baseUrl?: string;
```

Defined in: providers/openai-responses.ts:138

Base URL for OpenAI API (default: https://api.openai.com)

### estimateTokens?

```ts
optional estimateTokens?: (text) => number;
```

Defined in: providers/openai-responses.ts:148

Optional token estimator (e.g. tiktoken) for the debug payload

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

Defined in: providers/openai-responses.ts:142

Default max output tokens (default: 4096) → `max_output_tokens`

### model?

```ts
optional model?: string;
```

Defined in: providers/openai-responses.ts:140

Default model (default: gpt-6-sol)

### organization?

```ts
optional organization?: string;
```

Defined in: providers/openai-responses.ts:146

OpenAI organization ID (optional)

### timeout?

```ts
optional timeout?: number;
```

Defined in: providers/openai-responses.ts:144

Request timeout in milliseconds (default: 120000)
