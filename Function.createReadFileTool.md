---
title: "createReadFileTool"
parent: Functions
nav_order: 1
---


# Function: createReadFileTool()

```ts
function createReadFileTool(options?): Tool<ReadFileInput>;
```

Defined in: tools/builtin/read-file.ts:193

Factory function to create a read_file tool with custom options

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `options?` | \{ `allowedExtensions?`: `string`[]; `baseDir?`: `string`; `maxContentSize?`: `number`; `maxFileSize?`: `number`; `truncateIfLarge?`: `boolean`; \} | - |
| `options.allowedExtensions?` | `string`[] | List of allowed file extensions (e.g., ['.ts', '.js', '.json']) |
| `options.baseDir?` | `string` | Base directory to resolve relative paths against |
| `options.maxContentSize?` | `number` | Maximum content size returned to agent in bytes (default: 100KB). Content larger than this is truncated. |
| `options.maxFileSize?` | `number` | Maximum file size to read in bytes (default: 10MB). Files larger than this are rejected entirely. |
| `options.truncateIfLarge?` | `boolean` | Whether to truncate large content (true) or reject (false). Default: true |

## Returns

[`Tool`](Interface.Tool.md)\<[`ReadFileInput`](Interface.ReadFileInput.md)\>
