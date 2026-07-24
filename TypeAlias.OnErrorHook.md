---
title: "OnErrorHook"
parent: Type Aliases
nav_order: 1
---


# Type Alias: OnErrorHook

```ts
type OnErrorHook = (context) => 
  | undefined
  | Promise<undefined>
  | ErrorHookResult
| Promise<ErrorHookResult>;
```

Defined in: hooks/types.ts:354

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

  \| `undefined`
  \| `Promise`\<`undefined`\>
  \| [`ErrorHookResult`](Interface.ErrorHookResult.md)
  \| `Promise`\<[`ErrorHookResult`](Interface.ErrorHookResult.md)\>
