---
title: "RetryConfig"
parent: Interfaces
nav_order: 1
---


# Interface: RetryConfig

Defined in: rate-limit/types.ts:81

Configuration for automatic retry

## Properties

### backoffMultiplier?

```ts
optional backoffMultiplier?: number;
```

Defined in: rate-limit/types.ts:104

Multiplier for exponential backoff

#### Default

```ts
2
```

### baseDelayMs?

```ts
optional baseDelayMs?: number;
```

Defined in: rate-limit/types.ts:92

Base delay between retries in milliseconds

#### Default

```ts
1000
```

### isRetryable?

```ts
optional isRetryable?: (error) => boolean;
```

Defined in: rate-limit/types.ts:116

Custom function to determine if an error is retryable
If not provided, uses default logic (429, 5xx, connection errors)

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `error` | `Error` |

#### Returns

`boolean`

### jitter?

```ts
optional jitter?: boolean;
```

Defined in: rate-limit/types.ts:110

Whether to add random jitter to delays

#### Default

```ts
true
```

### maxDelayMs?

```ts
optional maxDelayMs?: number;
```

Defined in: rate-limit/types.ts:98

Maximum delay between retries in milliseconds

#### Default

```ts
60000
```

### maxRetries?

```ts
optional maxRetries?: number;
```

Defined in: rate-limit/types.ts:86

Maximum number of retry attempts

#### Default

```ts
3
```

### onRetry?

```ts
optional onRetry?: (attempt, error, delayMs) => void;
```

Defined in: rate-limit/types.ts:121

Callback invoked before each retry attempt

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `attempt` | `number` |
| `error` | `Error` |
| `delayMs` | `number` |

#### Returns

`void`
