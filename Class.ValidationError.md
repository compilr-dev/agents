---
title: "ValidationError"
parent: Classes
nav_order: 1
---


# Class: ValidationError

Defined in: errors.ts:181

Error thrown when input validation fails.

## Example

```typescript
throw new ValidationError(
  'maxTokens must be a positive number',
  'maxTokens'
);
```

## Extends

- [`AgentError`](Class.AgentError.md)

## Constructors

### Constructor

```ts
new ValidationError(message, field): ValidationError;
```

Defined in: errors.ts:182

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `message` | `string` |
| `field` | `string` |

#### Returns

`ValidationError`

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

### field

```ts
readonly field: string;
```

Defined in: errors.ts:184
