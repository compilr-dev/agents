---
title: "createTodoTools"
parent: Functions
nav_order: 1
---


# Function: createTodoTools()

```ts
function createTodoTools(store?): {
  store: TodoStore;
  todoClaim: Tool<TodoClaimInput>;
  todoHandoff: Tool<TodoHandoffInput>;
  todoRead: Tool<TodoReadInput>;
  todoWrite: Tool<TodoWriteInput>;
};
```

Defined in: tools/builtin/todo.ts:466

Factory to create todo tools with a custom store

## Parameters

| Parameter | Type |
| ------ | ------ |
| `store?` | [`TodoStore`](Class.TodoStore.md) |

## Returns

```ts
{
  store: TodoStore;
  todoClaim: Tool<TodoClaimInput>;
  todoHandoff: Tool<TodoHandoffInput>;
  todoRead: Tool<TodoReadInput>;
  todoWrite: Tool<TodoWriteInput>;
}
```

| Name | Type | Defined in |
| ------ | ------ | ------ |
| `store` | [`TodoStore`](Class.TodoStore.md) | tools/builtin/todo.ts:471 |
| `todoClaim` | [`Tool`](Interface.Tool.md)\<`TodoClaimInput`\> | tools/builtin/todo.ts:469 |
| `todoHandoff` | [`Tool`](Interface.Tool.md)\<`TodoHandoffInput`\> | tools/builtin/todo.ts:470 |
| `todoRead` | [`Tool`](Interface.Tool.md)\<[`TodoReadInput`](Interface.TodoReadInput.md)\> | tools/builtin/todo.ts:468 |
| `todoWrite` | [`Tool`](Interface.Tool.md)\<[`TodoWriteInput`](Interface.TodoWriteInput.md)\> | tools/builtin/todo.ts:467 |
