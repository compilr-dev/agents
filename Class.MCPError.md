---
title: "MCPError"
parent: Classes
nav_order: 1
---


# Class: MCPError

Defined in: mcp/errors.ts:43

Error thrown for MCP-related failures

## Example

```typescript
throw new MCPError(
  'Failed to connect to server',
  'filesystem',
  MCPErrorCode.CONNECTION_FAILED
);
```

## Extends

- [`AgentError`](Class.AgentError.md)

## Constructors

### Constructor

```ts
new MCPError(
   message, 
   serverName, 
   code, 
   cause?): MCPError;
```

Defined in: mcp/errors.ts:44

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `message` | `string` |
| `serverName` | `string` |
| `code` | [`MCPErrorCode`](Enumeration.MCPErrorCode.md) |
| `cause?` | `Error` |

#### Returns

`MCPError`

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

### code

```ts
readonly code: MCPErrorCode;
```

Defined in: mcp/errors.ts:47

### serverName

```ts
readonly serverName: string;
```

Defined in: mcp/errors.ts:46

## Methods

### isRetryable()

```ts
isRetryable(): boolean;
```

Defined in: mcp/errors.ts:64

Check if the error is retryable (connection/timeout issues)

#### Returns

`boolean`

### isSDKNotInstalled()

```ts
isSDKNotInstalled(): boolean;
```

Defined in: mcp/errors.ts:57

Check if the error is due to missing SDK

#### Returns

`boolean`
