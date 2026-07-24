---
title: "BeforeIterationHook"
parent: Type Aliases
nav_order: 1
---


# Type Alias: BeforeIterationHook

```ts
type BeforeIterationHook = (context) => 
  | undefined
  | Promise<undefined>
  | {
  skip: true;
}
  | Promise<{
  skip: true;
}>;
```

Defined in: hooks/types.ts:70

Hook called before each iteration starts.

Can be used for:
- Logging iteration boundaries
- Custom iteration budget tracking
- Early termination checks

## Parameters

| Parameter | Type |
| ------ | ------ |
| `context` | [`IterationHookContext`](Interface.IterationHookContext.md) |

## Returns

  \| `undefined`
  \| `Promise`\<`undefined`\>
  \| \{
  `skip`: `true`;
\}
  \| `Promise`\<\{
  `skip`: `true`;
\}\>

void, or { skip: true } to skip this iteration
