---
title: "RateLimiterStats"
parent: Interfaces
nav_order: 1
---


# Interface: RateLimiterStats

Defined in: rate-limit/types.ts:41

Rate limiter statistics

## Properties

### availableRequests

```ts
availableRequests: number;
```

Defined in: rate-limit/types.ts:45

Current number of available request tokens

### availableTokens

```ts
availableTokens: number;
```

Defined in: rate-limit/types.ts:50

Current number of available LLM tokens

### currentConcurrent

```ts
currentConcurrent: number;
```

Defined in: rate-limit/types.ts:55

Current number of concurrent requests

### rateLimitHits

```ts
rateLimitHits: number;
```

Defined in: rate-limit/types.ts:70

Number of times rate limit was hit

### totalRequests

```ts
totalRequests: number;
```

Defined in: rate-limit/types.ts:60

Total requests made

### totalTokens

```ts
totalTokens: number;
```

Defined in: rate-limit/types.ts:65

Total tokens consumed

### totalWaitTimeMs

```ts
totalWaitTimeMs: number;
```

Defined in: rate-limit/types.ts:75

Total time spent waiting due to rate limits (ms)
