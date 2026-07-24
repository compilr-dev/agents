---
title: "LLMRetryConfig"
parent: Interfaces
nav_order: 1
---


# Interface: LLMRetryConfig

Defined in: utils/index.ts:52

Configuration for LLM retry behavior

## Properties

### baseDelayMs?

```ts
optional baseDelayMs?: number;
```

Defined in: utils/index.ts:71

Base delay in milliseconds for exponential backoff.
Actual delay = min(baseDelayMs * 2^attempt, maxDelayMs) + jitter

#### Default

```ts
1000
```

### enabled?

```ts
optional enabled?: boolean;
```

Defined in: utils/index.ts:57

Enable/disable automatic retry.

#### Default

```ts
true
```

### maxAttempts?

```ts
optional maxAttempts?: number;
```

Defined in: utils/index.ts:64

Maximum number of retry attempts (not including initial attempt).
Total attempts = maxAttempts + 1

#### Default

```ts
10
```

### maxDelayMs?

```ts
optional maxDelayMs?: number;
```

Defined in: utils/index.ts:77

Maximum delay in milliseconds (cap for exponential growth).

#### Default

```ts
30000
```
