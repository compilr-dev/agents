---
title: "createKillShellTool"
parent: Functions
nav_order: 1
---


# Function: createKillShellTool()

```ts
function createKillShellTool(options?): Tool<KillShellInput>;
```

Defined in: tools/builtin/kill-shell.ts:102

Factory function to create a killShell tool with custom shell manager

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `options?` | \{ `shellManager?`: [`ShellManager`](Class.ShellManager.md); \} | - |
| `options.shellManager?` | [`ShellManager`](Class.ShellManager.md) | Custom shell manager to use |

## Returns

[`Tool`](Interface.Tool.md)\<`KillShellInput`\>
