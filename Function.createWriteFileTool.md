---
title: "createWriteFileTool"
parent: Functions
nav_order: 1
---


# Function: createWriteFileTool()

```ts
function createWriteFileTool(options?): Tool<WriteFileInput>;
```

Defined in: tools/builtin/write-file.ts:126

Factory function to create a write_file tool with custom options

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `options?` | \{ `allowedExtensions?`: `string`[]; `baseDir?`: `string`; `blockedPaths?`: `string`[]; `maxContentSize?`: `number`; \} | - |
| `options.allowedExtensions?` | `string`[] | List of allowed file extensions (e.g., ['.ts', '.js', '.json']) |
| `options.baseDir?` | `string` | Base directory to resolve relative paths against |
| `options.blockedPaths?` | `string`[] | Directories that cannot be written to |
| `options.maxContentSize?` | `number` | Maximum content size in bytes (default: 10MB) |

## Returns

[`Tool`](Interface.Tool.md)\<[`WriteFileInput`](Interface.WriteFileInput.md)\>
