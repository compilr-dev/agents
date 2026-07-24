---
title: "GeminiProvider"
parent: Classes
nav_order: 1
---


# Class: GeminiProvider

Defined in: providers/gemini-native.ts:83

GeminiNativeProvider implements LLMProvider using the native Google Gen AI SDK

Benefits over OpenAI-compatible endpoint:
- Automatic thought signature handling for Gemini 3
- Native streaming support
- Full access to Gemini-specific features

## Implements

- [`LLMProvider`](Interface.LLMProvider.md)

## Constructors

### Constructor

```ts
new GeminiProvider(config): GeminiNativeProvider;
```

Defined in: providers/gemini-native.ts:91

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `config` | [`GeminiProviderConfig`](Interface.GeminiProviderConfig.md) |

#### Returns

`GeminiNativeProvider`

## Properties

### name

```ts
readonly name: "gemini" = 'gemini';
```

Defined in: providers/gemini-native.ts:84

Provider identifier (e.g., 'claude', 'openai', 'gemini')

#### Implementation of

[`LLMProvider`](Interface.LLMProvider.md).[`name`](Interface.LLMProvider.md#name)

## Methods

### chat()

```ts
chat(messages, options?): AsyncIterable<StreamChunk>;
```

Defined in: providers/gemini-native.ts:110

Send messages and stream the response

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `messages` | [`Message`](Interface.Message.md)[] |
| `options?` | [`ChatOptions`](Interface.ChatOptions.md) |

#### Returns

`AsyncIterable`\<[`StreamChunk`](Interface.StreamChunk.md)\>

#### Implementation of

[`LLMProvider`](Interface.LLMProvider.md).[`chat`](Interface.LLMProvider.md#chat)

### countTokens()

```ts
countTokens(messages): Promise<number>;
```

Defined in: providers/gemini-native.ts:233

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

Defined in: providers/gemini-native.ts:99

Get the current default model ID.

#### Returns

`string`

#### Implementation of

[`LLMProvider`](Interface.LLMProvider.md).[`getModel`](Interface.LLMProvider.md#getmodel)

### setModel()

```ts
setModel(modelId): void;
```

Defined in: providers/gemini-native.ts:103

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
