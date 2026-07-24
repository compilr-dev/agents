---
title: "RetryStats"
parent: Classes
nav_order: 1
---


# Class: RetryStats

Defined in: rate-limit/retry.ts:271

Retry statistics collector

## Constructors

### Constructor

```ts
new RetryStats(): RetryStats;
```

#### Returns

`RetryStats`

## Methods

### createConfig()

```ts
createConfig(baseConfig?): RetryConfig;
```

Defined in: rate-limit/retry.ts:282

Create retry config that tracks statistics

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `baseConfig` | [`RetryConfig`](Interface.RetryConfig.md) |

#### Returns

[`RetryConfig`](Interface.RetryConfig.md)

### getStats()

```ts
getStats(): {
  attempts: number;
  averageRetries: number;
  failures: number;
  lastError?: string;
  retries: number;
  successes: number;
  successRate: number;
  totalDelayMs: number;
};
```

Defined in: rate-limit/retry.ts:313

Get statistics

#### Returns

```ts
{
  attempts: number;
  averageRetries: number;
  failures: number;
  lastError?: string;
  retries: number;
  successes: number;
  successRate: number;
  totalDelayMs: number;
}
```

| Name | Type | Defined in |
| ------ | ------ | ------ |
| `attempts` | `number` | rate-limit/retry.ts:314 |
| `averageRetries` | `number` | rate-limit/retry.ts:320 |
| `failures` | `number` | rate-limit/retry.ts:316 |
| `lastError?` | `string` | rate-limit/retry.ts:321 |
| `retries` | `number` | rate-limit/retry.ts:317 |
| `successes` | `number` | rate-limit/retry.ts:315 |
| `successRate` | `number` | rate-limit/retry.ts:319 |
| `totalDelayMs` | `number` | rate-limit/retry.ts:318 |

### recordAttempt()

```ts
recordAttempt(success): void;
```

Defined in: rate-limit/retry.ts:301

Record an attempt outcome

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `success` | `boolean` |

#### Returns

`void`

### reset()

```ts
reset(): void;
```

Defined in: rate-limit/retry.ts:338

Reset statistics

#### Returns

`void`
