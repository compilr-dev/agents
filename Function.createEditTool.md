---
title: "createEditTool"
parent: Functions
nav_order: 1
---


# Function: createEditTool()

```ts
function createEditTool(options?): Tool<EditInput>;
```

Defined in: tools/builtin/edit.ts:209

Factory function to create an edit tool with custom options

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `options?` | \{ `allowedExtensions?`: `string`[]; `baseDir?`: `string`; `disallowedPaths?`: `string`[]; \} | - |
| `options.allowedExtensions?` | `string`[] | Allowed file extensions (if specified, only these can be edited) |
| `options.baseDir?` | `string` | Base directory to resolve relative paths against |
| `options.disallowedPaths?` | `string`[] | Disallowed paths (files that cannot be edited) |

## Returns

[`Tool`](Interface.Tool.md)\<[`EditInput`](Interface.EditInput.md)\>
