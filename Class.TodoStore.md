---
title: "TodoStore"
parent: Classes
nav_order: 1
---


# Class: TodoStore

Defined in: tools/builtin/todo.ts:111

TodoStore manages the in-memory task list

## Constructors

### Constructor

```ts
new TodoStore(): TodoStore;
```

#### Returns

`TodoStore`

## Methods

### add()

```ts
add(todo): TodoItem;
```

Defined in: tools/builtin/todo.ts:190

Add a single todo

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `todo` | \{ `activeForm?`: `string`; `blockedBy?`: `number`[]; `content`: `string`; `owner?`: `string`; `priority?`: `number`; `status`: [`TodoStatus`](TypeAlias.TodoStatus.md); \} |
| `todo.activeForm?` | `string` |
| `todo.blockedBy?` | `number`[] |
| `todo.content` | `string` |
| `todo.owner?` | `string` |
| `todo.priority?` | `number` |
| `todo.status` | [`TodoStatus`](TypeAlias.TodoStatus.md) |

#### Returns

[`TodoItem`](Interface.TodoItem.md)

### clear()

```ts
clear(): void;
```

Defined in: tools/builtin/todo.ts:241

Clear all todos

#### Returns

`void`

### getAll()

```ts
getAll(): TodoItem[];
```

Defined in: tools/builtin/todo.ts:118

Get all todos

#### Returns

[`TodoItem`](Interface.TodoItem.md)[]

### getByOwner()

```ts
getByOwner(owner): TodoItem[];
```

Defined in: tools/builtin/todo.ts:149

Get todos filtered by owner

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `owner` | `string` | Agent ID, or 'unassigned' for tasks without owner |

#### Returns

[`TodoItem`](Interface.TodoItem.md)[]

### getByStatus()

```ts
getByStatus(status): TodoItem[];
```

Defined in: tools/builtin/todo.ts:141

Get todos filtered by status

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `status` | [`TodoStatus`](TypeAlias.TodoStatus.md) |

#### Returns

[`TodoItem`](Interface.TodoItem.md)[]

### getCounts()

```ts
getCounts(): Record<TodoStatus, number>;
```

Defined in: tools/builtin/todo.ts:248

Get count by status

#### Returns

`Record`\<[`TodoStatus`](TypeAlias.TodoStatus.md), `number`\>

### getCountsByOwner()

```ts
getCountsByOwner(): Record<string, number>;
```

Defined in: tools/builtin/todo.ts:265

Get counts by owner
Returns a map of owner ID to count
'unassigned' key contains count of todos without owner

#### Returns

`Record`\<`string`, `number`\>

### remove()

```ts
remove(id): boolean;
```

Defined in: tools/builtin/todo.ts:234

Remove a todo by ID

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |

#### Returns

`boolean`

### setAll()

```ts
setAll(todos): void;
```

Defined in: tools/builtin/todo.ts:159

Replace all todos with a new list

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `todos` | \{ `activeForm?`: `string`; `blockedBy?`: `number`[]; `content`: `string`; `owner?`: `string`; `priority?`: `number`; `status`: [`TodoStatus`](TypeAlias.TodoStatus.md); \}[] |

#### Returns

`void`

### update()

```ts
update(id, updates): TodoItem | null;
```

Defined in: tools/builtin/todo.ts:218

Update a todo by ID

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |
| `updates` | `Partial`\<`Omit`\<[`TodoItem`](Interface.TodoItem.md), `"id"` \| `"createdAt"`\>\> |

#### Returns

[`TodoItem`](Interface.TodoItem.md) \| `null`
