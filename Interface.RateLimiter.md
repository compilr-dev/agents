---
title: "RateLimiter"
parent: Interfaces
nav_order: 1
---


# Interface: RateLimiter

Defined in: rate-limit/types.ts:162

Rate limiter interface

## Methods

### acquire()

```ts
acquire(estimatedTokens?): Promise<AcquireResult>;
```

Defined in: rate-limit/types.ts:170

Acquire permission to make a request
Waits if necessary (unless throwOnLimit is true)

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `estimatedTokens?` | `number` | Estimated tokens for the request (optional) |

#### Returns

`Promise`\<[`AcquireResult`](Interface.AcquireResult.md)\>

Acquire result

### canAcquire()

```ts
canAcquire(estimatedTokens?): boolean;
```

Defined in: rate-limit/types.ts:198

Check if a request can be made immediately

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `estimatedTokens?` | `number` |

#### Returns

`boolean`

### getStats()

```ts
getStats(): RateLimiterStats;
```

Defined in: rate-limit/types.ts:188

Get current rate limiter statistics

#### Returns

[`RateLimiterStats`](Interface.RateLimiterStats.md)

### release()

```ts
release(): void;
```

Defined in: rate-limit/types.ts:175

Release a concurrent request slot

#### Returns

`void`

### reportUsage()

```ts
reportUsage(tokens): void;
```

Defined in: rate-limit/types.ts:183

Report actual token usage after request completes
Used to update token bucket

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `tokens` | `number` | Actual tokens used |

#### Returns

`void`

### reset()

```ts
reset(): void;
```

Defined in: rate-limit/types.ts:193

Reset the rate limiter

#### Returns

`void`
