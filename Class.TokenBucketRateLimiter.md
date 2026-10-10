---
title: "TokenBucketRateLimiter"
parent: Classes
nav_order: 1
---


# Class: TokenBucketRateLimiter

Defined in: rate-limit/limiter.ts:48

Token bucket rate limiter implementation

Uses the token bucket algorithm:
- Tokens are added at a constant rate (refill rate)
- Each request consumes tokens
- If insufficient tokens, request waits or fails

## Example

```typescript
const limiter = new TokenBucketRateLimiter({
  requestsPerMinute: 60,
  tokensPerMinute: 100000,
  maxConcurrent: 5,
});

// Before making a request
await limiter.acquire(1000); // estimated tokens

try {
  const result = await makeRequest();
  limiter.reportUsage(actualTokens);
} finally {
  limiter.release();
}
```

## Implements

- [`RateLimiter`](Interface.RateLimiter.md)

## Constructors

### Constructor

```ts
new TokenBucketRateLimiter(config?): TokenBucketRateLimiter;
```

Defined in: rate-limit/limiter.ts:75

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `config` | [`RateLimiterConfig`](Interface.RateLimiterConfig.md) |

#### Returns

`TokenBucketRateLimiter`

## Methods

### acquire()

```ts
acquire(estimatedTokens?): Promise<AcquireResult>;
```

Defined in: rate-limit/limiter.ts:93

Acquire permission to make a request

#### Parameters

| Parameter | Type | Default value |
| ------ | ------ | ------ |
| `estimatedTokens` | `number` | `0` |

#### Returns

`Promise`\<[`AcquireResult`](Interface.AcquireResult.md)\>

#### Implementation of

[`RateLimiter`](Interface.RateLimiter.md).[`acquire`](Interface.RateLimiter.md#acquire)

### canAcquire()

```ts
canAcquire(estimatedTokens?): boolean;
```

Defined in: rate-limit/limiter.ts:190

Check if a request can be made immediately

#### Parameters

| Parameter | Type | Default value |
| ------ | ------ | ------ |
| `estimatedTokens` | `number` | `0` |

#### Returns

`boolean`

#### Implementation of

[`RateLimiter`](Interface.RateLimiter.md).[`canAcquire`](Interface.RateLimiter.md#canacquire)

### getStats()

```ts
getStats(): RateLimiterStats;
```

Defined in: rate-limit/limiter.ts:149

Get current statistics

#### Returns

[`RateLimiterStats`](Interface.RateLimiterStats.md)

#### Implementation of

[`RateLimiter`](Interface.RateLimiter.md).[`getStats`](Interface.RateLimiter.md#getstats)

### release()

```ts
release(): void;
```

Defined in: rate-limit/limiter.ts:123

Release a concurrent request slot

#### Returns

`void`

#### Implementation of

[`RateLimiter`](Interface.RateLimiter.md).[`release`](Interface.RateLimiter.md#release)

### reportUsage()

```ts
reportUsage(tokens): void;
```

Defined in: rate-limit/limiter.ts:135

Report actual token usage

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `tokens` | `number` |

#### Returns

`void`

#### Implementation of

[`RateLimiter`](Interface.RateLimiter.md).[`reportUsage`](Interface.RateLimiter.md#reportusage)

### reset()

```ts
reset(): void;
```

Defined in: rate-limit/limiter.ts:165

Reset the rate limiter

#### Returns

`void`

#### Implementation of

[`RateLimiter`](Interface.RateLimiter.md).[`reset`](Interface.RateLimiter.md#reset)
