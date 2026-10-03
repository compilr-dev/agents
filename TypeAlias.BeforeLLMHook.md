---
title: "BeforeLLMHook"
parent: Type Aliases
nav_order: 1
---


# Type Alias: BeforeLLMHook

```ts
type BeforeLLMHook = (context) => 
  | void
  | BeforeLLMHookResult
| Promise<void | BeforeLLMHookResult>;
```

Defined in: hooks/types.ts:157

Hook called before LLM call.

Can be used for:
- Prompt transformation/injection
- Tool filtering
- Request logging
- Caching checks

## Parameters

| Parameter | Type |
| ------ | ------ |
| `context` | [`LLMHookContext`](Interface.LLMHookContext.md) |

## Returns

  \| `void`
  \| [`BeforeLLMHookResult`](Interface.BeforeLLMHookResult.md)
  \| `Promise`\<`void` \| [`BeforeLLMHookResult`](Interface.BeforeLLMHookResult.md)\>

void to proceed unchanged, or modified messages/tools
