---
title: "AfterIterationHook"
parent: Type Aliases
nav_order: 1
---


# Type Alias: AfterIterationHook

```ts
type AfterIterationHook = (context) => void | Promise<void>;
```

Defined in: hooks/types.ts:82

Hook called after each iteration completes.

Can be used for:
- Logging iteration results
- Metrics collection
- State snapshots

## Parameters

| Parameter | Type |
| ------ | ------ |
| `context` | [`IterationHookContext`](Interface.IterationHookContext.md) & \{ `completedWithText`: `boolean`; `toolCalls`: \{ `input`: `Record`\<`string`, `unknown`\>; `name`: `string`; `result`: [`ToolExecutionResult`](Interface.ToolExecutionResult.md); \}[]; \} |

## Returns

`void` \| `Promise`\<`void`\>
