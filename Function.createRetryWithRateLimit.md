---
title: "createRetryWithRateLimit"
parent: Functions
nav_order: 1
---


# Function: createRetryWithRateLimit()

```ts
function createRetryWithRateLimit(rateLimiter, config?): <T>(fn, estimatedTokens?) => Promise<T>;
```

Defined in: rate-limit/retry.ts:199

Create a retry wrapper that also integrates with rate limiting

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `rateLimiter` | [`RateLimiter`](Interface.RateLimiter.md) | Rate limiter instance |
| `config` | [`RetryConfig`](Interface.RetryConfig.md) | Retry configuration |

## Returns

Function wrapper with retry and rate limiting

\<`T`\>(`fn`, `estimatedTokens?`) => `Promise`\<`T`\>

## Example

```typescript
const limiter = createRateLimiter({ requestsPerMinute: 60 });
const retryWithLimit = createRetryWithRateLimit(limiter, { maxRetries: 3 });

const result = await retryWithLimit(
  () => provider.chat(messages, options),
  1000 // estimated tokens
);
```
