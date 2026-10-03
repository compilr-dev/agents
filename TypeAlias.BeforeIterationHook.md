---
title: "BeforeIterationHook"
parent: Type Aliases
nav_order: 1
---


# Type Alias: BeforeIterationHook

```ts
type BeforeIterationHook = (context) => 
  | void
  | {
  skip: true;
}
  | Promise<
  | void
  | {
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

  \| `void`
  \| \{
  `skip`: `true`;
\}
  \| `Promise`\<
  \| `void`
  \| \{
  `skip`: `true`;
\}\>

void, or { skip: true } to skip this iteration
