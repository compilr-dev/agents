---
title: "OpenAICompatibleProvider"
parent: Classes
nav_order: 1
---


# Abstract Class: OpenAICompatibleProvider

Defined in: providers/openai-compatible.ts:137

Abstract base class for OpenAI-compatible LLM providers

Provides shared implementation for providers that use the OpenAI
chat completions API format (OpenAI, Ollama, Azure OpenAI, Gemini).

## Extended by

- [`OllamaProvider`](Class.OllamaProvider.md)
- [`OpenAIProvider`](Class.OpenAIProvider.md)
- [`GeminiLegacyProvider`](Class.GeminiLegacyProvider.md)
- [`TogetherProvider`](Class.TogetherProvider.md)
- [`GroqProvider`](Class.GroqProvider.md)
- [`FireworksProvider`](Class.FireworksProvider.md)
- [`PerplexityProvider`](Class.PerplexityProvider.md)
- [`OpenRouterProvider`](Class.OpenRouterProvider.md)

## Implements

- [`LLMProvider`](Interface.LLMProvider.md)

## Constructors

### Constructor

```ts
new OpenAICompatibleProvider(config): OpenAICompatibleProvider;
```

Defined in: providers/openai-compatible.ts:149

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `config` | [`OpenAICompatibleConfig`](Interface.OpenAICompatibleConfig.md) |

#### Returns

`OpenAICompatibleProvider`

## Properties

### name

```ts
abstract readonly name: string;
```

Defined in: providers/openai-compatible.ts:141

Provider name (e.g., 'openai', 'ollama', 'gemini')

#### Implementation of

[`LLMProvider`](Interface.LLMProvider.md).[`name`](Interface.LLMProvider.md#name)

## Methods

### chat()

```ts
chat(messages, options?): AsyncIterable<StreamChunk>;
```

Defined in: providers/openai-compatible.ts:222

Stream chat completion from the provider

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `messages` | [`Message`](Interface.Message.md)[] | Conversation messages |
| `options?` | [`ChatOptions`](Interface.ChatOptions.md) | Chat options (thinking is ignored for non-Claude providers) |

#### Returns

`AsyncIterable`\<[`StreamChunk`](Interface.StreamChunk.md)\>

#### Implementation of

[`LLMProvider`](Interface.LLMProvider.md).[`chat`](Interface.LLMProvider.md#chat)

### countTokens()

```ts
countTokens(messages): Promise<number>;
```

Defined in: providers/openai-compatible.ts:646

Count tokens in messages using tiktoken (cl100k_base encoding)

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `messages` | [`Message`](Interface.Message.md)[] |

#### Returns

`Promise`\<`number`\>

#### Implementation of

[`LLMProvider`](Interface.LLMProvider.md).[`countTokens`](Interface.LLMProvider.md#counttokens)

### getModel()

```ts
getModel(): string;
```

Defined in: providers/openai-compatible.ts:158

Get the current default model ID.

#### Returns

`string`

#### Implementation of

[`LLMProvider`](Interface.LLMProvider.md).[`getModel`](Interface.LLMProvider.md#getmodel)

### setModel()

```ts
setModel(modelId): void;
```

Defined in: providers/openai-compatible.ts:162

Change the default model for subsequent calls. Same provider only.
Takes effect on the next chat() call, not mid-stream.

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `modelId` | `string` | The new model ID (e.g., 'claude-opus-4-20250514') |

#### Returns

`void`

#### Implementation of

[`LLMProvider`](Interface.LLMProvider.md).[`setModel`](Interface.LLMProvider.md#setmodel)
