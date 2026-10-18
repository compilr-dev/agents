---
title: "MockProvider"
parent: Classes
nav_order: 1
---


# Class: MockProvider

Defined in: providers/mock.ts:82

MockProvider for testing agents without API calls.

Responses are consumed in order (FIFO queue).

## Implements

- [`LLMProvider`](Interface.LLMProvider.md)

## Constructors

### Constructor

```ts
new MockProvider(config?): MockProvider;
```

Defined in: providers/mock.ts:93

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `config` | [`MockProviderConfig`](Interface.MockProviderConfig.md) |

#### Returns

`MockProvider`

## Properties

### name

```ts
readonly name: "mock" = 'mock';
```

Defined in: providers/mock.ts:83

Provider identifier (e.g., 'claude', 'openai', 'gemini')

#### Implementation of

[`LLMProvider`](Interface.LLMProvider.md).[`name`](Interface.LLMProvider.md#name)

## Methods

### addError()

```ts
addError(error): this;
```

Defined in: providers/mock.ts:131

Queue an error to be thrown on the next call

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `error` | `Error` |

#### Returns

`this`

### addResponse()

```ts
addResponse(response): this;
```

Defined in: providers/mock.ts:109

Add a response (text string or structured response with tool calls)

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `response` | `string` \| [`MockResponse`](Interface.MockResponse.md) |

#### Returns

`this`

### addResponses()

```ts
addResponses(responses): this;
```

Defined in: providers/mock.ts:121

Add multiple responses at once

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `responses` | (`string` \| [`MockResponse`](Interface.MockResponse.md))[] |

#### Returns

`this`

### chat()

```ts
chat(messages, options?): AsyncIterable<StreamChunk>;
```

Defined in: providers/mock.ts:177

Stream chat response

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

Defined in: providers/mock.ts:256

Count tokens using tiktoken (cl100k_base encoding)

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `messages` | [`Message`](Interface.Message.md)[] |

#### Returns

`Promise`\<`number`\>

#### Implementation of

[`LLMProvider`](Interface.LLMProvider.md).[`countTokens`](Interface.LLMProvider.md#counttokens)

### getCallCount()

```ts
getCallCount(): number;
```

Defined in: providers/mock.ts:139

Get number of times chat() was called

#### Returns

`number`

### getCallHistory()

```ts
getCallHistory(): readonly {
  messages: Message[];
  options?: ChatOptions;
}[];
```

Defined in: providers/mock.ts:146

Get the history of all calls made

#### Returns

readonly \{
  `messages`: [`Message`](Interface.Message.md)[];
  `options?`: [`ChatOptions`](Interface.ChatOptions.md);
\}[]

### getLastCall()

```ts
getLastCall(): 
  | {
  messages: Message[];
  options?: ChatOptions;
}
  | undefined;
```

Defined in: providers/mock.ts:153

Get the last call made

#### Returns

  \| \{
  `messages`: [`Message`](Interface.Message.md)[];
  `options?`: [`ChatOptions`](Interface.ChatOptions.md);
\}
  \| `undefined`

### getModel()

```ts
getModel(): string;
```

Defined in: providers/mock.ts:98

Get the current default model ID.

#### Returns

`string`

#### Implementation of

[`LLMProvider`](Interface.LLMProvider.md).[`getModel`](Interface.LLMProvider.md#getmodel)

### hasResponses()

```ts
hasResponses(): boolean;
```

Defined in: providers/mock.ts:170

Check if there are any queued responses

#### Returns

`boolean`

### reset()

```ts
reset(): this;
```

Defined in: providers/mock.ts:160

Clear all queued responses and call history

#### Returns

`this`

### setModel()

```ts
setModel(modelId): void;
```

Defined in: providers/mock.ts:102

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
