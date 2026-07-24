---
title: "ToolLoopError"
parent: Classes
nav_order: 1
---


# Class: ToolLoopError

Defined in: errors.ts:218

Error thrown when the agent is stuck in a tool call loop.

This occurs when the same tool is called with identical input
multiple times consecutively, indicating the agent is not
processing the tool results properly.

## Example

```typescript
throw new ToolLoopError('read_file', 3);
```

## Extends

- [`AgentError`](Class.AgentError.md)

## Constructors

### Constructor

```ts
new ToolLoopError(
   toolName, 
   consecutiveCalls, 
   input?): ToolLoopError;
```

Defined in: errors.ts:219

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `toolName` | `string` |
| `consecutiveCalls` | `number` |
| `input?` | `Record`\<`string`, `unknown`\> |

#### Returns

`ToolLoopError`

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

### consecutiveCalls

```ts
readonly consecutiveCalls: number;
```

Defined in: errors.ts:221

### input?

```ts
readonly optional input?: Record<string, unknown>;
```

Defined in: errors.ts:222

### toolName

```ts
readonly toolName: string;
```

Defined in: errors.ts:220
