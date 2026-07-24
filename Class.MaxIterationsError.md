---
title: "MaxIterationsError"
parent: Classes
nav_order: 1
---


# Class: MaxIterationsError

Defined in: errors.ts:199

Error thrown when the agentic loop exceeds max iterations.

## Example

```typescript
throw new MaxIterationsError(10);
```

## Extends

- [`AgentError`](Class.AgentError.md)

## Constructors

### Constructor

```ts
new MaxIterationsError(maxIterations): MaxIterationsError;
```

Defined in: errors.ts:200

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `maxIterations` | `number` |

#### Returns

`MaxIterationsError`

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

### maxIterations

```ts
readonly maxIterations: number;
```

Defined in: errors.ts:200
