---
title: "TodoWriteInput"
parent: Interfaces
nav_order: 1
---


# Interface: TodoWriteInput

Defined in: tools/builtin/todo.ts:71

Input for TodoWrite tool

## Properties

### todos

```ts
todos: {
  activeForm?: string;
  blockedBy?: number[];
  content: string;
  owner?: string;
  priority?: number;
  status: TodoStatus;
}[];
```

Defined in: tools/builtin/todo.ts:75

The complete list of todos (replaces existing list)

#### activeForm?

```ts
optional activeForm?: string;
```

#### blockedBy?

```ts
optional blockedBy?: number[];
```

#### content

```ts
content: string;
```

#### owner?

```ts
optional owner?: string;
```

#### priority?

```ts
optional priority?: number;
```

#### status

```ts
status: TodoStatus;
```
