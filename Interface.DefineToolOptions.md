---
title: "DefineToolOptions"
parent: Interfaces
nav_order: 1
---


# Interface: DefineToolOptions\<T\>

Defined in: tools/define.ts:10

Options for defining a tool

## Type Parameters

| Type Parameter |
| ------ |
| `T` *extends* `object` |

## Properties

### description

```ts
description: string;
```

Defined in: tools/define.ts:19

Description of what the tool does (shown to LLM)

### execute

```ts
execute: (input) => Promise<ToolExecutionResult>;
```

Defined in: tools/define.ts:29

Function that executes the tool

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `input` | `T` |

#### Returns

`Promise`\<[`ToolExecutionResult`](Interface.ToolExecutionResult.md)\>

### inputSchema

```ts
inputSchema: ToolInputSchema;
```

Defined in: tools/define.ts:24

JSON Schema for the tool's input parameters

### name

```ts
name: string;
```

Defined in: tools/define.ts:14

Unique name for the tool

### parallel?

```ts
optional parallel?: boolean;
```

Defined in: tools/define.ts:37

If true, multiple calls to this tool can execute in parallel.
When the LLM requests multiple parallel-safe tools in one response,
they will be executed concurrently using Promise.all.
Default: false (sequential execution)

### readonly?

```ts
optional readonly?: boolean;
```

Defined in: tools/define.ts:52

If true, this tool performs no side effects (only reads data).
Read-only tools are automatically batched for parallel execution
even in a mixed batch with write tools.
Default: false

### repeatable?

```ts
optional repeatable?: boolean;
```

Defined in: tools/define.ts:57

If true, this tool is exempt from tool-loop detection (repeated identical
calls are always legitimate). Default: false.

### silent?

```ts
optional silent?: boolean;
```

Defined in: tools/define.ts:44

If true, this tool runs silently without spinner updates or result output.
Used for internal housekeeping tools like todo_read, suggest, etc.
Default: false (normal visibility)
