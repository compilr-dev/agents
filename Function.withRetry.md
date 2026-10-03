---
title: "withRetry"
parent: Functions
nav_order: 1
---


# Function: withRetry()

```ts
function withRetry<T>(fn, config?): Promise<T>;
```

Defined in: rate-limit/retry.ts:140

Retry a function with exponential backoff

## Type Parameters

| Type Parameter |
| ------ |
| `T` |

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `fn` | () => `Promise`\<`T`\> | Function to retry |
| `config` | [`RetryConfig`](Interface.RetryConfig.md) | Retry configuration |

## Returns

`Promise`\<`T`\>

Result of the function

## Example

```typescript
const result = await withRetry(
  () => provider.chat(messages, options),
  {
    maxRetries: 3,
    baseDelayMs: 1000,
    onRetry: (attempt, error, delay) => {
      console.log(`Retry ${attempt} after ${delay}ms: ${error.message}`);
    },
  }
);
```
