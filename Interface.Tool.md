---
title: "Tool"
parent: Interfaces
nav_order: 1
---


# Interface: Tool\<T\>

Defined in: tools/types.ts:119

A tool that the agent can call during conversations.

Tools are the primary way agents interact with the outside world — reading
files, running commands, querying APIs, etc. Each tool has a definition
(name, description, parameters) that the LLM sees, and an execute function
that runs when the LLM decides to call it.

Use `defineTool()` to create tools with type-safe parameters.

## Example

```typescript
const readFileTool: Tool<{ path: string }> = {
  definition: {
    name: 'read_file',
    description: 'Read the contents of a file',
    parameters: {
      type: 'object',
      properties: { path: { type: 'string', description: 'File path' } },
      required: ['path'],
    },
  },
  execute: async ({ path }) => {
    const content = await fs.readFile(path, 'utf-8');
    return { content };
  },
  readonly: true,  // Safe for parallel execution
};
```

## Type Parameters

| Type Parameter | Default type | Description |
| ------ | ------ | ------ |
| `T` | `object` | The type of the tool's input parameters |

## Properties

### definition

```ts
definition: ToolDefinition;
```

Defined in: tools/types.ts:120

### execute

```ts
execute: ToolHandler<T>;
```

Defined in: tools/types.ts:121

### parallel?

```ts
optional parallel?: boolean;
```

Defined in: tools/types.ts:128

If true, multiple calls to this tool can execute in parallel.
When the LLM requests multiple parallel-safe tools in one response,
they will be executed concurrently using Promise.all.
Default: false (sequential execution)

### readonly?

```ts
optional readonly?: boolean;
```

Defined in: tools/types.ts:141

If true, this tool performs no side effects (only reads data).
Read-only tools are automatically batched for parallel execution
even in a mixed batch with write tools.
Default: false

### repeatable?

```ts
optional repeatable?: boolean;
```

Defined in: tools/types.ts:148

If true, this tool is exempt from tool-loop detection — repeated identical
calls are always legitimate (e.g. genuinely idempotent pollers). Most
polling tools do NOT need this: loop detection is result-aware, so calls
that return changing output don't trip. Default: false.

### silent?

```ts
optional silent?: boolean;
```

Defined in: tools/types.ts:134

If true, this tool runs silently without spinner updates or result output.
Used for internal housekeeping tools like todo_read, suggest, etc.
Default: false (normal visibility)
