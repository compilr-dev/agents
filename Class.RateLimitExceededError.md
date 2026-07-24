---
title: "RateLimitExceededError"
parent: Classes
nav_order: 1
---


# Class: RateLimitExceededError

Defined in: rate-limit/types.ts:204

Error thrown when rate limit is exceeded and throwOnLimit is true

## Extends

- `Error`

## Constructors

### Constructor

```ts
new RateLimitExceededError(message, estimatedWaitMs): RateLimitExceededError;
```

Defined in: rate-limit/types.ts:205

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `message` | `string` |
| `estimatedWaitMs` | `number` |

#### Returns

`RateLimitExceededError`

#### Overrides

```ts
Error.constructor
```

## Properties

### estimatedWaitMs

```ts
readonly estimatedWaitMs: number;
```

Defined in: rate-limit/types.ts:207
