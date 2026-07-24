---
title: "wrapToolExecute"
parent: Functions
nav_order: 1
---


# Function: wrapToolExecute()

```ts
function wrapToolExecute<T>(fn): (input) => Promise<ToolExecutionResult>;
```

Defined in: tools/define.ts:119

Wrap an async function to catch errors and return ToolExecutionResult

## Type Parameters

| Type Parameter |
| ------ |
| `T` *extends* `object` |

## Parameters

| Parameter | Type |
| ------ | ------ |
| `fn` | (`input`) => `Promise`\<`unknown`\> |

## Returns

(`input`) => `Promise`\<[`ToolExecutionResult`](Interface.ToolExecutionResult.md)\>
