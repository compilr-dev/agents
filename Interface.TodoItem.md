---
title: "TodoItem"
parent: Interfaces
nav_order: 1
---


# Interface: TodoItem

Defined in: tools/builtin/todo.ts:19

A single todo item

## Properties

### activeForm?

```ts
optional activeForm?: string;
```

Defined in: tools/builtin/todo.ts:38

Active form of the task (present continuous, e.g., "Implementing feature")

### blockedBy?

```ts
optional blockedBy?: number[];
```

Defined in: tools/builtin/todo.ts:55

1-based task numbers this task is blocked by.
References positions in the todo array.

### content

```ts
content: string;
```

Defined in: tools/builtin/todo.ts:28

Task content/description (imperative form)

### createdAt

```ts
createdAt: Date;
```

Defined in: tools/builtin/todo.ts:60

Creation timestamp

### id

```ts
id: string;
```

Defined in: tools/builtin/todo.ts:23

Unique identifier for the todo

### owner?

```ts
optional owner?: string;
```

Defined in: tools/builtin/todo.ts:49

Owner agent ID (e.g., 'pm', 'arch', 'dev')
If undefined/null, the task is unassigned

### priority?

```ts
optional priority?: number;
```

Defined in: tools/builtin/todo.ts:43

Optional priority (higher = more important)

### status

```ts
status: TodoStatus;
```

Defined in: tools/builtin/todo.ts:33

Current status of the task

### updatedAt

```ts
updatedAt: Date;
```

Defined in: tools/builtin/todo.ts:65

Last update timestamp
