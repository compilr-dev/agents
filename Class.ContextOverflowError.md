---
title: "ContextOverflowError"
parent: Classes
nav_order: 1
---


# Class: ContextOverflowError

Defined in: errors.ts:258

Error thrown when context window cannot be reduced sufficiently.

This occurs when:
- Multiple summarization rounds fail to reduce context below target
- Content is too large even after aggressive filtering

## Example

```typescript
throw new ContextOverflowError(
  'Unable to reduce context below 90% after 3 summarization rounds',
  0.95,  // current utilization
  3      // rounds attempted
);
```

## Extends

- [`AgentError`](Class.AgentError.md)

## Constructors

### Constructor

```ts
new ContextOverflowError(
   message, 
   utilization, 
   roundsAttempted?): ContextOverflowError;
```

Defined in: errors.ts:259

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `message` | `string` |
| `utilization` | `number` |
| `roundsAttempted?` | `number` |

#### Returns

`ContextOverflowError`

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

### roundsAttempted?

```ts
readonly optional roundsAttempted?: number;
```

Defined in: errors.ts:262

### utilization

```ts
readonly utilization: number;
```

Defined in: errors.ts:261
