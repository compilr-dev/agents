---
title: "defineTool"
parent: Functions
nav_order: 1
---


# Function: defineTool()

```ts
function defineTool<T>(options): Tool<T>;
```

Defined in: tools/define.ts:82

Define a tool with type-safe input handling

## Type Parameters

| Type Parameter |
| ------ |
| `T` *extends* `object` |

## Parameters

| Parameter | Type |
| ------ | ------ |
| `options` | [`DefineToolOptions`](Interface.DefineToolOptions.md)\<`T`\> |

## Returns

[`Tool`](Interface.Tool.md)\<`T`\>

## Example

```typescript
const readFile = defineTool({
  name: 'read_file',
  description: 'Read the contents of a file',
  inputSchema: {
    type: 'object',
    properties: {
      path: { type: 'string', description: 'File path to read' },
    },
    required: ['path'],
  },
  execute: async ({ path }) => {
    const content = await fs.readFile(path, 'utf-8');
    return { success: true, result: content };
  },
});
```
