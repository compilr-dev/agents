---
title: "createIsolatedTodoStore"
parent: Functions
nav_order: 1
---


# Function: createIsolatedTodoStore()

```ts
function createIsolatedTodoStore(): TodoStore;
```

Defined in: tools/builtin/todo.ts:733

Create a new isolated TodoStore instance.

Use this when you need state isolation between parallel operations,
such as concurrent sub-agent executions. This prevents state leakage
between parallel runs.

Inspired by LangGraph issue #6446: Parallel subgraphs with shared
state keys cause InvalidUpdateError.

## Returns

[`TodoStore`](Class.TodoStore.md)

## Example

```typescript
// For parallel sub-agents, create isolated stores
const store1 = createIsolatedTodoStore();
const store2 = createIsolatedTodoStore();

// Each sub-agent uses its own store
await Promise.all([
  runWithStore(store1, task1),
  runWithStore(store2, task2),
]);
```
