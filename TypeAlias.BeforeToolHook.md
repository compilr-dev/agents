---
title: "BeforeToolHook"
parent: Type Aliases
nav_order: 1
---


# Type Alias: BeforeToolHook

```ts
type BeforeToolHook = (context) => 
  | undefined
  | Promise<undefined>
  | BeforeToolHookResult
| Promise<BeforeToolHookResult>;
```

Defined in: hooks/types.ts:259

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

  \| `undefined`
  \| `Promise`\<`undefined`\>
  \| [`BeforeToolHookResult`](Interface.BeforeToolHookResult.md)
  \| `Promise`\<[`BeforeToolHookResult`](Interface.BeforeToolHookResult.md)\>

void to proceed, or skip/modify options
