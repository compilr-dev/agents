---
title: "ToolError"
parent: Classes
nav_order: 1
---


# Class: ToolError

Defined in: errors.ts:141

Error thrown when a tool execution fails.

## Example

```typescript
throw new ToolError(
  'File not found: /path/to/file.txt',
  'read_file',
  originalError
);
```

## Extends

- [`AgentError`](Class.AgentError.md)

## Extended by

- [`ToolTimeoutError`](Class.ToolTimeoutError.md)

## Constructors

### Constructor

```ts
new ToolError(
   message, 
   toolName, 
   cause?): ToolError;
```

Defined in: errors.ts:142

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `message` | `string` |
| `toolName` | `string` |
| `cause?` | `Error` |

#### Returns

`ToolError`

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

### toolName

```ts
readonly toolName: string;
```

Defined in: errors.ts:144
