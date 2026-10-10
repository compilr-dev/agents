---
title: "BeforeToolHook"
parent: Type Aliases
nav_order: 1
---


# Type Alias: BeforeToolHook

```ts
type BeforeToolHook = (context) => 
  | void
  | BeforeToolHookResult
| Promise<void | BeforeToolHookResult>;
```

Defined in: hooks/types.ts:274

Hook called before tool execution (after permissions and guardrails).

Can be used for:
- Custom validation
- Input transformation
- Execution mocking for tests
- Rate limiting

## Parameters

| Parameter | Type |
| ------ | ------ |
| `context` | [`ToolHookContext`](Interface.ToolHookContext.md) |

## Returns

  \| `void`
  \| [`BeforeToolHookResult`](Interface.BeforeToolHookResult.md)
  \| `Promise`\<`void` \| [`BeforeToolHookResult`](Interface.BeforeToolHookResult.md)\>

void to proceed, or skip/modify options
