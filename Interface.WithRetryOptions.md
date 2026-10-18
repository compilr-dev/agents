---
title: "WithRetryOptions"
parent: Interfaces
nav_order: 1
---


# Interface: WithRetryOptions\<E\>

Defined in: utils/index.ts:93

Options for the withRetry function

## Type Parameters

| Type Parameter |
| ------ |
| `E` *extends* `Error` |

## Properties

### baseDelayMs?

```ts
optional baseDelayMs?: number;
```

Defined in: utils/index.ts:102

Base delay in milliseconds (default: 1000)

### isRetryable?

```ts
optional isRetryable?: (error) => boolean;
```

Defined in: utils/index.ts:112

Function to determine if an error is retryable

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `error` | `E` |

#### Returns

`boolean`

### maxAttempts?

```ts
optional maxAttempts?: number;
```

Defined in: utils/index.ts:97

Maximum retry attempts (default: 10)

### maxDelayMs?

```ts
optional maxDelayMs?: number;
```

Defined in: utils/index.ts:107

Maximum delay cap in milliseconds (default: 30000)

### onExhausted?

```ts
optional onExhausted?: (attempts, error) => void;
```

Defined in: utils/index.ts:122

Callback invoked when all retries are exhausted

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `attempts` | `number` |
| `error` | `E` |

#### Returns

`void`

### onRetry?

```ts
optional onRetry?: (attempt, maxAttempts, error, delayMs) => void;
```

Defined in: utils/index.ts:117

Callback invoked before each retry attempt

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `attempt` | `number` |
| `maxAttempts` | `number` |
| `error` | `E` |
| `delayMs` | `number` |

#### Returns

`void`

### signal?

```ts
optional signal?: AbortSignal;
```

Defined in: utils/index.ts:127

AbortSignal to cancel retries
