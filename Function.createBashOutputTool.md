---
title: "createBashOutputTool"
parent: Functions
nav_order: 1
---


# Function: createBashOutputTool()

```ts
function createBashOutputTool(options?): Tool<BashOutputInput>;
```

Defined in: tools/builtin/bash-output.ts:127

Factory function to create a bashOutput tool with custom shell manager

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `options?` | \{ `shellManager?`: [`ShellManager`](Class.ShellManager.md); \} | - |
| `options.shellManager?` | [`ShellManager`](Class.ShellManager.md) | Custom shell manager to use |

## Returns

[`Tool`](Interface.Tool.md)\<`BashOutputInput`\>
