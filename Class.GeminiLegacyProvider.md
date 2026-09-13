---
title: "GeminiLegacyProvider"
parent: Classes
nav_order: 1
---


# Class: GeminiLegacyProvider

Defined in: providers/gemini.ts:53

Google Gemini LLM Provider

Provides streaming chat completion using Google's Gemini models
via the OpenAI-compatible API endpoint.
Supports gemini-2.0-flash, gemini-1.5-flash, gemini-1.5-pro, and others.

## Extends

- [`OpenAICompatibleProvider`](Class.OpenAICompatibleProvider.md)

## Constructors

### Constructor

```ts
new GeminiLegacyProvider(config?): GeminiProvider;
```

Defined in: providers/gemini.ts:58

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `config` | [`GeminiLegacyProviderConfig`](Interface.GeminiLegacyProviderConfig.md) |

#### Returns

`GeminiProvider`

#### Overrides

[`OpenAICompatibleProvider`](Class.OpenAICompatibleProvider.md).[`constructor`](Class.OpenAICompatibleProvider.md#constructor)

## Properties

### name

```ts
readonly name: "gemini" = 'gemini';
```

Defined in: providers/gemini.ts:54

Provider name (e.g., 'openai', 'ollama', 'gemini')

#### Overrides

[`OpenAICompatibleProvider`](Class.OpenAICompatibleProvider.md).[`name`](Class.OpenAICompatibleProvider.md#name)

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

#### Inherited from

[`OpenAICompatibleProvider`](Class.OpenAICompatibleProvider.md).[`chat`](Class.OpenAICompatibleProvider.md#chat)

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

#### Inherited from

[`OpenAICompatibleProvider`](Class.OpenAICompatibleProvider.md).[`countTokens`](Class.OpenAICompatibleProvider.md#counttokens)

### getModel()

```ts
getModel(): string;
```

Defined in: providers/openai-compatible.ts:158

Get the current default model ID.

#### Returns

`string`

#### Inherited from

[`OpenAICompatibleProvider`](Class.OpenAICompatibleProvider.md).[`getModel`](Class.OpenAICompatibleProvider.md#getmodel)

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

#### Inherited from

[`OpenAICompatibleProvider`](Class.OpenAICompatibleProvider.md).[`setModel`](Class.OpenAICompatibleProvider.md#setmodel)
