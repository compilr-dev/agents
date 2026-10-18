---
title: "ToolHandler"
parent: Type Aliases
nav_order: 1
---


# Type Alias: ToolHandler\<T\>

```ts
type ToolHandler<T> = (input, context?) => Promise<ToolExecutionResult>;
```

Defined in: tools/types.ts:82

Tool handler function type

## Type Parameters

| Type Parameter | Default type |
| ------ | ------ |
| `T` | `object` |

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `input` | `T` | The tool input parameters |
| `context?` | `ToolExecutionContext` | Optional execution context for streaming |

## Returns

`Promise`\<[`ToolExecutionResult`](Interface.ToolExecutionResult.md)\>
