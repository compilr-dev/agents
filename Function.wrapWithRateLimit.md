---
title: "wrapWithRateLimit"
parent: Functions
nav_order: 1
---


# Function: wrapWithRateLimit()

```ts
function wrapWithRateLimit(provider, config?): RateLimitedProvider;
```

Defined in: rate-limit/provider-wrapper.ts:162

Create a rate-limited provider wrapper

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `provider` | [`LLMProvider`](Interface.LLMProvider.md) | The base LLM provider |
| `config?` | [`RateLimitRetryConfig`](Interface.RateLimitRetryConfig.md) | Rate limit and retry configuration |

## Returns

[`RateLimitedProvider`](Class.RateLimitedProvider.md)

Wrapped provider with rate limiting and retry

## Example

```typescript
const provider = createClaudeProvider();
const rateLimited = wrapWithRateLimit(provider, {
  rateLimit: { requestsPerMinute: 60 },
  retry: { maxRetries: 3 },
});
```
