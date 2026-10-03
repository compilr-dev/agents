---
title: "OpenAIProvider"
parent: Classes
nav_order: 1
---


# Class: OpenAIProvider

Defined in: providers/openai.ts:231

OpenAI provider — ONE `ProviderType`, two transports.

Routes each call by model id (and base URL) to either `/v1/responses` or
`/v1/chat/completions`. See `openai-models.ts` for the rules.

⚠️ WHY ONE PROVIDER TYPE, not a second `'openai-responses'` arm. A new arm would have to be
added to `ProviderType`, `createProviderFromType`, `ENV_PROVIDER_MAP`, `PROVIDER_METADATA`,
the tier-mapping provider list, Desktop's `PROVIDERS` array and every settings/credential map
in both hosts — all to express "the same vendor, the same key, the same account". Worse, it
would break the hot-switch: Desktop's `classifyConfigChange()` returns `'rebuild'` when the
provider string differs and `'hot-model'` otherwise, so `gpt-5.5 → gpt-6-sol` would become a
full provider rebuild. With one arm it stays a model-only change: `setModel()` on every live
agent, the router picks the other transport on the next `chat()`, and history survives because
it is plain text (measured — OpenAI, unlike Claude, accepts a replay with reasoning dropped).

## Example

```typescript
const provider = createOpenAIProvider();            // gpt-6-sol → /v1/responses
provider.setModel('gpt-5.5');                        // → /v1/chat/completions, same instance
```

## Implements

- [`LLMProvider`](Interface.LLMProvider.md)

## Constructors

### Constructor

```ts
new OpenAIProvider(config?): OpenAIProvider;
```

Defined in: providers/openai.ts:240

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `config` | [`OpenAIProviderConfig`](Interface.OpenAIProviderConfig.md) |

#### Returns

`OpenAIProvider`

## Properties

### name

```ts
readonly name: "openai" = 'openai';
```

Defined in: providers/openai.ts:232

Provider identifier (e.g., 'claude', 'openai', 'gemini')

#### Implementation of

[`LLMProvider`](Interface.LLMProvider.md).[`name`](Interface.LLMProvider.md#name)

## Methods

### chat()

```ts
chat(messages, options?): AsyncIterable<StreamChunk>;
```

Defined in: providers/openai.ts:272

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

#### Implementation of

[`LLMProvider`](Interface.LLMProvider.md).[`chat`](Interface.LLMProvider.md#chat)

### countTokens()

```ts
countTokens(messages): Promise<number>;
```

Defined in: providers/openai.ts:263

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

Defined in: providers/openai.ts:255

The model lives on the router, never on a transport — so a switch cannot desynchronise.

#### Returns

`string`

#### Implementation of

[`LLMProvider`](Interface.LLMProvider.md).[`getModel`](Interface.LLMProvider.md#getmodel)

### routeOf()

```ts
routeOf(model?): OpenAIRoute;
```

Defined in: providers/openai.ts:268

Which transport a model id resolves to. Exposed for tests and diagnostics.

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `model?` | `string` |

#### Returns

[`OpenAIRoute`](TypeAlias.OpenAIRoute.md)

### setModel()

```ts
setModel(modelId): void;
```

Defined in: providers/openai.ts:259

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
