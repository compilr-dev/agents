---
title: "AfterLLMHook"
parent: Type Aliases
nav_order: 1
---


# Type Alias: AfterLLMHook

```ts
type AfterLLMHook = (context) => undefined | Promise<undefined>;
```

Defined in: hooks/types.ts:207

Hook called after LLM response is received.

Can be used for:
- Response logging
- Token tracking
- Response validation
- Metrics collection

## Parameters

| Parameter | Type |
| ------ | ------ |
| `context` | [`AfterLLMHookContext`](Interface.AfterLLMHookContext.md) |

## Returns

`undefined` \| `Promise`\<`undefined`\>
