---
title: "withRetryGenerator"
parent: Functions
nav_order: 1
---


# Function: withRetryGenerator()

```ts
function withRetryGenerator<T, E>(fn, options?): AsyncGenerator<T, void, undefined>;
```

Defined in: utils/index.ts:245

Create a retryable async generator for streaming responses

This is specifically designed for streaming LLM responses where we need to
retry the entire stream if it fails partway through.

## Type Parameters

| Type Parameter | Default type |
| ------ | ------ |
| `T` | - |
| `E` *extends* `Error` | `Error` |

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `fn` | () => `AsyncIterable`\<`T`\> | Function that returns an async iterable |
| `options` | [`WithRetryOptions`](Interface.WithRetryOptions.md)\<`E`\> | Retry options |

## Returns

`AsyncGenerator`\<`T`, `void`, `undefined`\>

Async generator that retries on failure
