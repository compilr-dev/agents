---
title: "AfterToolHook"
parent: Type Aliases
nav_order: 1
---


# Type Alias: AfterToolHook

```ts
type AfterToolHook = (context) => 
  | void
  | AfterToolHookResult
| Promise<void | AfterToolHookResult>;
```

Defined in: hooks/types.ts:312

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

  \| `void`
  \| [`AfterToolHookResult`](Interface.AfterToolHookResult.md)
  \| `Promise`\<`void` \| [`AfterToolHookResult`](Interface.AfterToolHookResult.md)\>
