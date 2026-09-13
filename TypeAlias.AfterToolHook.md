---
title: "AfterToolHook"
parent: Type Aliases
nav_order: 1
---


# Type Alias: AfterToolHook

```ts
type AfterToolHook = (context) => 
  | undefined
  | Promise<undefined>
  | AfterToolHookResult
| Promise<AfterToolHookResult>;
```

Defined in: hooks/types.ts:297

Hook called after tool execution.

Can be used for:
- Result transformation
- Logging and metrics
- Result validation
- Error enrichment

## Parameters

| Parameter | Type |
| ------ | ------ |
| `context` | [`AfterToolHookContext`](Interface.AfterToolHookContext.md) |

## Returns

  \| `undefined`
  \| `Promise`\<`undefined`\>
  \| [`AfterToolHookResult`](Interface.AfterToolHookResult.md)
  \| `Promise`\<[`AfterToolHookResult`](Interface.AfterToolHookResult.md)\>
