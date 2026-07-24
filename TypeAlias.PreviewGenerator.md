---
title: "PreviewGenerator"
parent: Type Aliases
nav_order: 1
---


# Type Alias: PreviewGenerator

```ts
type PreviewGenerator = (toolName, input) => string | undefined;
```

Defined in: permissions/types.ts:157

Preview generator for permission requests

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `toolName` | `string` | Name of the tool |
| `input` | `Record`\<`string`, `unknown`\> | Tool input arguments |

## Returns

`string` \| `undefined`

Human-readable preview of the operation
