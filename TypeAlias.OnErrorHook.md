---
title: "OnErrorHook"
parent: Type Aliases
nav_order: 1
---


# Type Alias: OnErrorHook

```ts
type OnErrorHook = (context) => 
  | void
  | ErrorHookResult
| Promise<void | ErrorHookResult>;
```

Defined in: hooks/types.ts:369

Hook called when an error occurs.

Can be used for:
- Error logging
- Error transformation
- Recovery strategies
- Alerting

## Parameters

| Parameter | Type |
| ------ | ------ |
| `context` | [`ErrorHookContext`](Interface.ErrorHookContext.md) |

## Returns

  \| `void`
  \| [`ErrorHookResult`](Interface.ErrorHookResult.md)
  \| `Promise`\<`void` \| [`ErrorHookResult`](Interface.ErrorHookResult.md)\>
