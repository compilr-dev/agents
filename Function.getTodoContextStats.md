---
title: "getTodoContextStats"
parent: Functions
nav_order: 1
---


# Function: getTodoContextStats()

```ts
function getTodoContextStats(messages): {
  estimatedTokensSaved: number;
  todoReadCalls: number;
  todoWriteCalls: number;
};
```

Defined in: tools/builtin/todo.ts:841

Get statistics about todo tool usage in messages

## Parameters

| Parameter | Type |
| ------ | ------ |
| `messages` | \{ `content`: `unknown`; `role`: `string`; \}[] |

## Returns

```ts
{
  estimatedTokensSaved: number;
  todoReadCalls: number;
  todoWriteCalls: number;
}
```

| Name | Type | Defined in |
| ------ | ------ | ------ |
| `estimatedTokensSaved` | `number` | tools/builtin/todo.ts:844 |
| `todoReadCalls` | `number` | tools/builtin/todo.ts:843 |
| `todoWriteCalls` | `number` | tools/builtin/todo.ts:842 |
