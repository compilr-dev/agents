---
title: "createGlobTool"
parent: Functions
nav_order: 1
---


# Function: createGlobTool()

```ts
function createGlobTool(options?): Tool<GlobInput>;
```

Defined in: tools/builtin/glob.ts:333

Factory function to create a glob tool with custom options

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `options?` | \{ `alwaysInclude?`: `string`[]; `baseDir?`: `string`; `excludeDirs?`: `string`[]; `ignorePatterns?`: `string`[]; \} | - |
| `options.alwaysInclude?` | `string`[] | Always include these patterns regardless of ignore |
| `options.baseDir?` | `string` | Base directory to resolve relative paths against |
| `options.excludeDirs?` | `string`[] | Override default excluded directories. Defaults to: node_modules, .git, dist, build, etc. |
| `options.ignorePatterns?` | `string`[] | Default patterns to ignore |

## Returns

[`Tool`](Interface.Tool.md)\<[`GlobInput`](Interface.GlobInput.md)\>
