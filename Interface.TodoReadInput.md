---
title: "TodoReadInput"
parent: Interfaces
nav_order: 1
---


# Interface: TodoReadInput

Defined in: tools/builtin/todo.ts:88

Input for TodoRead tool

## Properties

### includeCompleted?

```ts
optional includeCompleted?: boolean;
```

Defined in: tools/builtin/todo.ts:97

Include completed tasks (default: true)

### owner?

```ts
optional owner?: string;
```

Defined in: tools/builtin/todo.ts:105

Filter by owner (optional)
- Specific agent ID: Return only tasks owned by that agent
- 'unassigned': Return only tasks without an owner
- undefined: Return all tasks (no filter)

### status?

```ts
optional status?: TodoStatus;
```

Defined in: tools/builtin/todo.ts:92

Filter by status (optional)
