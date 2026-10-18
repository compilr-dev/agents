---
title: "coerceToolArgs"
parent: Functions
nav_order: 1
---


# Function: coerceToolArgs()

```ts
function coerceToolArgs(schema, args): Record<string, unknown>;
```

Defined in: tools/coerce.ts:39

Coerce `args` to match `schema`, recursing into declared object properties and array items.

Returns the ORIGINAL object when nothing needed changing, so a caller can compare by identity.

## Parameters

| Parameter | Type |
| ------ | ------ |
| `schema` | \| [`ToolInputSchema`](Interface.ToolInputSchema.md) \| `SchemaFragment` \| `undefined` |
| `args` | `Record`\<`string`, `unknown`\> |

## Returns

`Record`\<`string`, `unknown`\>
