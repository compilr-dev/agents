---
title: "OpenAIProvider"
parent: Classes
nav_order: 1
---


# Class: OpenAIProvider

Defined in: providers/openai.ts:55

OpenAI LLM Provider

Provides streaming chat completion using OpenAI models.
Supports GPT-4o, GPT-4o-mini, and other compatible models.

## Extends

- [`OpenAICompatibleProvider`](Class.OpenAICompatibleProvider.md)

## Constructors

### Constructor

```ts
new OpenAIProvider(config?): OpenAIProvider;
```

Defined in: providers/openai.ts:61

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `config` | [`OpenAIProviderConfig`](Interface.OpenAIProviderConfig.md) |

#### Returns

`OpenAIProvider`

#### Overrides

[`OpenAICompatibleProvider`](Class.OpenAICompatibleProvider.md).[`constructor`](Class.OpenAICompatibleProvider.md#constructor)

## Properties

### name

```ts
readonly name: "openai" = 'openai';
```

Defined in: providers/openai.ts:56

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
