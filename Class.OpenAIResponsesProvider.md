---
title: "OpenAIResponsesProvider"
parent: Classes
nav_order: 1
---


# Class: OpenAIResponsesProvider

Defined in: providers/openai-responses.ts:459

OpenAI Responses-API provider.

## Example

```typescript
const provider = createOpenAIResponsesProvider({ model: 'gpt-6-sol' });
```

## Implements

- [`LLMProvider`](Interface.LLMProvider.md)

## Constructors

### Constructor

```ts
new OpenAIResponsesProvider(config?): OpenAIResponsesProvider;
```

Defined in: providers/openai-responses.ts:475

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `config` | [`OpenAIResponsesProviderConfig`](Interface.OpenAIResponsesProviderConfig.md) |

#### Returns

`OpenAIResponsesProvider`

## Properties

### name

```ts
readonly name: "openai" = 'openai';
```

Defined in: providers/openai-responses.ts:465

⚠️ `'openai'`, not `'openai-responses'`. This string keys error classification, `llm_retry`
event payloads and `ProviderError.provider` across the SDK, CLI and Desktop. It names the
vendor, not the transport.

#### Implementation of

[`LLMProvider`](Interface.LLMProvider.md).[`name`](Interface.LLMProvider.md#name)

## Methods

### buildRequestBody()

```ts
buildRequestBody(messages, options?): ResponsesRequestBody;
```

Defined in: providers/openai-responses.ts:525

Build the request body.

What is deliberately NEVER sent, and why:
- `messages` — this endpoint takes `input`.
- `max_tokens` — measured *"Unknown parameter"*; the cap is `max_output_tokens`.
- `temperature` / `top_p` — measured *"'temperature' is not supported with this model"*.
  Dropped silently, exactly as `ClaudeProvider` drops them for the models that reject them.
- `stop` — Chat-Completions-shaped, no caller sets it, unmeasured here.
- `stream_options: {include_usage: true}` — Chat-Completions only; usage arrives on
  `response.completed`.

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `messages` | [`Message`](Interface.Message.md)[] |
| `options?` | [`ChatOptions`](Interface.ChatOptions.md) |

#### Returns

`ResponsesRequestBody`

### chat()

```ts
chat(messages, options?): AsyncIterable<StreamChunk>;
```

Defined in: providers/openai-responses.ts:557

Stream a response.

⚠️ EVERY tool-call chunk carries `toolCallId`. This endpoint announces BOTH calls of a
parallel turn (`output_item.added` ×2) before either has any arguments. Untagged, the
agent's accumulator closes whichever call it saw last: the two argument streams merge into
one buffer, `JSON.parse` fails, and BOTH calls are dropped while the turn is reported as
output-limit truncation — the user sees the agent say what it will do, then do nothing.
With the id set, the accumulator keys each call separately and we can stream both live.

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

Defined in: providers/openai-responses.ts:501

Count tokens in messages (optional, provider-specific)

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

Defined in: providers/openai-responses.ts:493

Get the current default model ID.

#### Returns

`string`

#### Implementation of

[`LLMProvider`](Interface.LLMProvider.md).[`getModel`](Interface.LLMProvider.md#getmodel)

### setModel()

```ts
setModel(modelId): void;
```

Defined in: providers/openai-responses.ts:497

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
