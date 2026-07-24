---
title: "ToolFallbackHandler"
parent: Type Aliases
nav_order: 1
---


# Type Alias: ToolFallbackHandler

```ts
type ToolFallbackHandler = (name, input, context?) => Promise<ToolExecutionResult | null>;
```

Defined in: tools/types.ts:160

Fallback handler for tools not found in the primary registry.
Used by meta-tools to transparently route calls to a secondary registry.

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `name` | `string` | Tool name that was not found |
| `input` | `Record`\<`string`, `unknown`\> | Tool input parameters |
| `context?` | `ToolExecutionContext` | Optional execution context |

## Returns

`Promise`\<[`ToolExecutionResult`](Interface.ToolExecutionResult.md) \| `null`\>

Result if handled, or null to return the default "not found" error
