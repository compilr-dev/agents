---
title: "ToolTimeoutError"
parent: Classes
nav_order: 1
---


# Class: ToolTimeoutError

Defined in: errors.ts:160

Error thrown when a tool execution times out.

## Example

```typescript
throw new ToolTimeoutError('read_file', 30000);
```

## Extends

- [`ToolError`](Class.ToolError.md)

## Constructors

### Constructor

```ts
new ToolTimeoutError(toolName, timeoutMs): ToolTimeoutError;
```

Defined in: errors.ts:161

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `toolName` | `string` |
| `timeoutMs` | `number` |

#### Returns

`ToolTimeoutError`

#### Overrides

[`ToolError`](Class.ToolError.md).[`constructor`](Class.ToolError.md#constructor)

## Properties

### cause?

```ts
readonly optional cause?: Error;
```

Defined in: errors.ts:17

#### Inherited from

[`ToolError`](Class.ToolError.md).[`cause`](Class.ToolError.md#cause)

### timeoutMs

```ts
readonly timeoutMs: number;
```

Defined in: errors.ts:163

### toolName

```ts
readonly toolName: string;
```

Defined in: errors.ts:162

#### Inherited from

[`ToolError`](Class.ToolError.md).[`toolName`](Class.ToolError.md#toolname)
