---
title: "cleanupTodoContextMessages"
parent: Functions
nav_order: 1
---


# Function: cleanupTodoContextMessages()

```ts
function cleanupTodoContextMessages<T>(messages, options?): T[];
```

Defined in: tools/builtin/todo.ts:763

Filter messages to remove redundant todo tool calls.
This helps prevent context bloat from repeated todo_write calls.

The function keeps only the last N todo_write calls (default: 1),
removing earlier ones to reduce context size.

## Type Parameters

| Type Parameter |
| ------ |
| `T` *extends* \{ `content`: `unknown`; `role`: `string`; \} |

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `messages` | `T`[] | Array of messages to filter |
| `options?` | [`TodoContextCleanupOptions`](Interface.TodoContextCleanupOptions.md) | Cleanup options |

## Returns

`T`[]

Filtered messages with redundant todo calls removed
