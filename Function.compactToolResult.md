---
title: "compactToolResult"
parent: Functions
nav_order: 1
---


# Function: compactToolResult()

```ts
function compactToolResult(
   toolName, 
   result, 
   input?): string;
```

Defined in: context/result-compactor.ts:34

Format a tool result as compact text for LLM context.
Falls back to JSON.stringify for unknown tools or non-object results.

## Parameters

| Parameter | Type |
| ------ | ------ |
| `toolName` | `string` |
| `result` | `unknown` |
| `input?` | `Record`\<`string`, `unknown`\> |

## Returns

`string`
