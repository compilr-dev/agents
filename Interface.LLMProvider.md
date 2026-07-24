---
title: "LLMProvider"
parent: Interfaces
nav_order: 1
---


# Interface: LLMProvider

Defined in: providers/types.ts:268

Interface for LLM providers. Implement this to add support for a new AI model.

Built-in providers: `ClaudeProvider`, `OpenAIProvider`, `GeminiProvider`,
`OllamaProvider`, `TogetherProvider`, `GroqProvider`, `FireworksProvider`,
`PerplexityProvider`, `OpenRouterProvider`.

For OpenAI-compatible APIs, extend `OpenAICompatibleProvider` instead of
implementing this interface directly.

## Properties

### name

```ts
readonly name: string;
```

Defined in: providers/types.ts:272

Provider identifier (e.g., 'claude', 'openai', 'gemini')

## Methods

### chat()

```ts
chat(messages, options?): AsyncIterable<StreamChunk>;
```

Defined in: providers/types.ts:280

Send messages to the LLM and stream the response.

Yields `StreamChunk` objects containing text fragments, tool calls,
usage stats, and other provider-specific data.

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `messages` | [`Message`](Interface.Message.md)[] |
| `options?` | [`ChatOptions`](Interface.ChatOptions.md) |

#### Returns

`AsyncIterable`\<[`StreamChunk`](Interface.StreamChunk.md)\>

### countTokens()?

```ts
optional countTokens(messages): Promise<number>;
```

Defined in: providers/types.ts:285

Count tokens in messages (optional, provider-specific)

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `messages` | [`Message`](Interface.Message.md)[] |

#### Returns

`Promise`\<`number`\>

### getModel()

```ts
getModel(): string;
```

Defined in: providers/types.ts:290

Get the current default model ID.

#### Returns

`string`

### setModel()

```ts
setModel(modelId): void;
```

Defined in: providers/types.ts:298

Change the default model for subsequent calls. Same provider only.
Takes effect on the next chat() call, not mid-stream.

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `modelId` | `string` | The new model ID (e.g., 'claude-opus-4-20250514') |

#### Returns

`void`
