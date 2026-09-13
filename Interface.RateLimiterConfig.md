---
title: "RateLimiterConfig"
parent: Interfaces
nav_order: 1
---


# Interface: RateLimiterConfig

Defined in: rate-limit/types.ts:10

Configuration for rate limiter

## Properties

### maxConcurrent?

```ts
optional maxConcurrent?: number;
```

Defined in: rate-limit/types.ts:29

Maximum concurrent requests
Set to 0 for unlimited

#### Default

```ts
0
```

### requestsPerMinute?

```ts
optional requestsPerMinute?: number;
```

Defined in: rate-limit/types.ts:15

Maximum requests per minute

#### Default

```ts
60
```

### throwOnLimit?

```ts
optional throwOnLimit?: boolean;
```

Defined in: rate-limit/types.ts:35

Whether to throw immediately when rate limited instead of waiting

#### Default

```ts
false
```

### tokensPerMinute?

```ts
optional tokensPerMinute?: number;
```

Defined in: rate-limit/types.ts:22

Maximum tokens per minute (for token-based limiting)
Set to 0 to disable token-based limiting

#### Default

```ts
0
```
