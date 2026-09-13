---
title: "createGrepTool"
parent: Functions
nav_order: 1
---


# Function: createGrepTool()

```ts
function createGrepTool(options?): Tool<GrepInput>;
```

Defined in: tools/builtin/grep.ts:472

Factory function to create a grep tool with custom options

TODO: Future enhancements could include:
- maxFileSize: Skip files larger than specified size

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `options?` | \{ `baseDir?`: `string`; `defaultExtensions?`: `string`[]; `excludeDirs?`: `string`[]; \} | - |
| `options.baseDir?` | `string` | Base directory to resolve relative paths against |
| `options.defaultExtensions?` | `string`[] | Default file extensions to search |
| `options.excludeDirs?` | `string`[] | Override default excluded directories. Defaults to: node_modules, .git, dist, build, etc. |

## Returns

[`Tool`](Interface.Tool.md)\<[`GrepInput`](Interface.GrepInput.md)\>
