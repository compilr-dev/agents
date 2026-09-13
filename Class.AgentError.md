---
title: "AgentError"
parent: Classes
nav_order: 1
---


# Class: AgentError

Defined in: errors.ts:14

Base error class for all agent-related errors.

## Extends

- `Error`

## Extended by

- [`ProviderError`](Class.ProviderError.md)
- [`ToolError`](Class.ToolError.md)
- [`ToolLoopError`](Class.ToolLoopError.md)
- [`ValidationError`](Class.ValidationError.md)
- [`MaxIterationsError`](Class.MaxIterationsError.md)
- [`AbortError`](Class.AbortError.md)
- [`ContextOverflowError`](Class.ContextOverflowError.md)
- [`MCPError`](Class.MCPError.md)

## Constructors

### Constructor

```ts
new AgentError(message, cause?): AgentError;
```

Defined in: errors.ts:15

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `message` | `string` |
| `cause?` | `Error` |

#### Returns

`AgentError`

#### Overrides

```ts
Error.constructor
```

## Properties

### cause?

```ts
readonly optional cause?: Error;
```

Defined in: errors.ts:17

#### Inherited from

```ts
Error.cause
```
