---
title: "ClaudeProvider"
parent: Classes
nav_order: 1
---


# Class: ClaudeProvider

Defined in: providers/claude.ts:206

LLM provider for Anthropic's Claude models (Opus, Sonnet, Haiku).

Supports streaming, tool use, prompt caching, extended context (1M tokens),
and token-efficient tool schemas.

## Examples

```typescript
const provider = new ClaudeProvider({
  apiKey: process.env.ANTHROPIC_API_KEY,
  model: 'claude-sonnet-4-20250514',
});

const agent = new Agent({
  provider,
  systemPrompt: 'You are a helpful assistant.',
});
```

```typescript
// Using the factory function
const provider = createClaudeProvider({
  apiKey: 'sk-ant-...',
  enableExtendedContext: true, // 1M token context
});
```

## Implements

- [`LLMProvider`](Interface.LLMProvider.md)

## Constructors

### Constructor

```ts
new ClaudeProvider(config): ClaudeProvider;
```

Defined in: providers/claude.ts:217

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `config` | [`ClaudeProviderConfig`](Interface.ClaudeProviderConfig.md) |

#### Returns

`ClaudeProvider`

## Properties

### name

```ts
readonly name: "claude" = 'claude';
```

Defined in: providers/claude.ts:207

Provider identifier (e.g., 'claude', 'openai', 'gemini')

#### Implementation of

[`LLMProvider`](Interface.LLMProvider.md).[`name`](Interface.LLMProvider.md#name)

## Methods

### chat()

```ts
chat(messages, options?): AsyncIterable<StreamChunk>;
```

Defined in: providers/claude.ts:244

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

Defined in: providers/claude.ts:363

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

Defined in: providers/claude.ts:233

Get the current default model ID.

#### Returns

`string`

#### Implementation of

[`LLMProvider`](Interface.LLMProvider.md).[`getModel`](Interface.LLMProvider.md#getmodel)

### setModel()

```ts
setModel(modelId): void;
```

Defined in: providers/claude.ts:237

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
