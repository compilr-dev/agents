---
title: "TodoContextCleanupOptions"
parent: Interfaces
nav_order: 1
---


# Interface: TodoContextCleanupOptions

Defined in: tools/builtin/todo.ts:740

Context cleanup options for todo tool calls

## Properties

### cleanReads?

```ts
optional cleanReads?: boolean;
```

Defined in: tools/builtin/todo.ts:749

Also clean up todo_read calls (default: false)

### keepLastN?

```ts
optional keepLastN?: number;
```

Defined in: tools/builtin/todo.ts:744

Keep only the last N todo_write calls (default: 1)
