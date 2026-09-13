---
title: "RateLimitedProvider"
parent: Classes
nav_order: 1
---


# Class: RateLimitedProvider

Defined in: rate-limit/provider-wrapper.ts:34

Wrapper that adds rate limiting and retry to any LLMProvider

## Example

```typescript
const provider = new ClaudeProvider({ apiKey: 'xxx' });
const wrapped = new RateLimitedProvider(provider, {
  rateLimit: {
    requestsPerMinute: 60,
    tokensPerMinute: 100000,
  },
  retry: {
    maxRetries: 3,
    baseDelayMs: 1000,
  },
});

// Use wrapped provider like normal
const agent = new Agent({ provider: wrapped });
```

## Implements

- [`LLMProvider`](Interface.LLMProvider.md)

## Constructors

### Constructor

```ts
new RateLimitedProvider(provider, config?): RateLimitedProvider;
```

Defined in: rate-limit/provider-wrapper.ts:41

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `provider` | [`LLMProvider`](Interface.LLMProvider.md) |
| `config` | [`RateLimitRetryConfig`](Interface.RateLimitRetryConfig.md) |

#### Returns

`RateLimitedProvider`

## Properties

### name

```ts
readonly name: string;
```

Defined in: rate-limit/provider-wrapper.ts:35

Provider identifier (e.g., 'claude', 'openai', 'gemini')

#### Implementation of

[`LLMProvider`](Interface.LLMProvider.md).[`name`](Interface.LLMProvider.md#name)

## Methods

### chat()

```ts
chat(messages, options?): AsyncIterable<StreamChunk>;
```

Defined in: rate-limit/provider-wrapper.ts:66

Send messages with rate limiting and retry

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

Defined in: rate-limit/provider-wrapper.ts:128

Count tokens with rate limiting

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

Defined in: rate-limit/provider-wrapper.ts:48

Get the current default model ID.

#### Returns

`string`

#### Implementation of

[`LLMProvider`](Interface.LLMProvider.md).[`getModel`](Interface.LLMProvider.md#getmodel)

### getRateLimiter()

```ts
getRateLimiter(): RateLimiter;
```

Defined in: rate-limit/provider-wrapper.ts:59

Get the rate limiter instance for statistics

#### Returns

[`RateLimiter`](Interface.RateLimiter.md)

### setModel()

```ts
setModel(modelId): void;
```

Defined in: rate-limit/provider-wrapper.ts:52

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
