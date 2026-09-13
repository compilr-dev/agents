---
title: "TogetherProvider"
parent: Classes
nav_order: 1
---


# Class: TogetherProvider

Defined in: providers/together.ts:53

Together AI LLM Provider

Provides streaming chat completion using Together AI models.
Supports Llama, Mistral, Qwen, and other open-source models.

## Extends

- [`OpenAICompatibleProvider`](Class.OpenAICompatibleProvider.md)

## Constructors

### Constructor

```ts
new TogetherProvider(config?): TogetherProvider;
```

Defined in: providers/together.ts:58

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `config` | [`TogetherProviderConfig`](Interface.TogetherProviderConfig.md) |

#### Returns

`TogetherProvider`

#### Overrides

[`OpenAICompatibleProvider`](Class.OpenAICompatibleProvider.md).[`constructor`](Class.OpenAICompatibleProvider.md#constructor)

## Properties

### name

```ts
readonly name: "together" = 'together';
```

Defined in: providers/together.ts:54

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
