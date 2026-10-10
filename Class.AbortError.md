---
title: "AbortError"
parent: Classes
nav_order: 1
---


# Class: AbortError

Defined in: errors.ts:235

Error thrown when a request is aborted via AbortSignal.

## Extends

- [`AgentError`](Class.AgentError.md)

## Constructors

### Constructor

```ts
new AbortError(message?): AbortError;
```

Defined in: errors.ts:236

#### Parameters

| Parameter | Type | Default value |
| ------ | ------ | ------ |
| `message` | `string` | `'Request was aborted'` |

#### Returns

`AbortError`

#### Overrides

[`AgentError`](Class.AgentError.md).[`constructor`](Class.AgentError.md#constructor)

## Properties

### cause?

```ts
readonly optional cause?: Error;
```

Defined in: errors.ts:17

#### Inherited from

[`AgentError`](Class.AgentError.md).[`cause`](Class.AgentError.md#cause)
