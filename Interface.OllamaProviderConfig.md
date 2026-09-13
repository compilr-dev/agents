---
title: "OllamaProviderConfig"
parent: Interfaces
nav_order: 1
---


# Interface: OllamaProviderConfig

Defined in: providers/ollama.ts:32

Configuration for OllamaProvider

## Properties

### baseUrl?

```ts
optional baseUrl?: string;
```

Defined in: providers/ollama.ts:34

Base URL for Ollama server (default: http://localhost:11434)

### estimateTokens?

```ts
optional estimateTokens?: (text) => number;
```

Defined in: providers/ollama.ts:44

Optional token estimator (e.g., tiktoken) for debug payload

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `text` | `string` |

#### Returns

`number`

### keepAlive?

```ts
optional keepAlive?: string;
```

Defined in: providers/ollama.ts:42

Keep alive duration for model in memory (default: '5m')

### maxTokens?

```ts
optional maxTokens?: number;
```

Defined in: providers/ollama.ts:38

Default max tokens (default: 4096)

### model?

```ts
optional model?: string;
```

Defined in: providers/ollama.ts:36

Default model to use (default: llama3.1)

### timeout?

```ts
optional timeout?: number;
```

Defined in: providers/ollama.ts:40

Request timeout in milliseconds (default: 120000)
