---
title: "createBashTool"
parent: Functions
nav_order: 1
---


# Function: createBashTool()

```ts
function createBashTool(options?): Tool<BashInput>;
```

Defined in: tools/builtin/bash.ts:671

Factory function to create a bash tool with custom options

SECURITY NOTE: The blockedCommands and allowedCommands options provide
ADVISORY filtering only. They are NOT a security boundary. Shell commands
can be obfuscated in many ways (quotes, escape sequences, command substitution,
environment variables, etc.) that bypass simple string matching.

For actual security isolation, use:
- Container/sandbox environments
- seccomp/AppArmor profiles
- Dedicated restricted shells (rbash)
- User namespace isolation

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `options?` | \{ `allowedCommands?`: `string`[]; `blockedCommands?`: `string`[]; `cwd?`: `string`; `fifoMode?`: `"warn"` \| `"block"` \| `"allow"`; `maxOutputSize?`: `number`; `restrictToAllowed?`: `boolean`; `shell?`: `string`; `shellManager?`: [`ShellManager`](Class.ShellManager.md); `timeout?`: `number`; \} | - |
| `options.allowedCommands?` | `string`[] | List of allowed commands - must match exactly (only used if restrictToAllowed is true) |
| `options.blockedCommands?` | `string`[] | Commands or patterns that are not allowed (ADVISORY ONLY - see security note) |
| `options.cwd?` | `string` | Default working directory |
| `options.fifoMode?` | `"warn"` \| `"block"` \| `"allow"` | How to handle FIFO/named pipe usage detection - 'warn': Add warning to result (default) - 'block': Return error if FIFO usage detected - 'allow': Ignore FIFO detection |
| `options.maxOutputSize?` | `number` | Maximum output size returned to agent (default: 50KB). Larger outputs are truncated to prevent memory bloat. |
| `options.restrictToAllowed?` | `boolean` | If true, only allow commands in allowedCommands list (ADVISORY ONLY) |
| `options.shell?` | `string` | Shell to use (default: /bin/bash) |
| `options.shellManager?` | [`ShellManager`](Class.ShellManager.md) | Custom shell manager for background processes |
| `options.timeout?` | `number` | Default timeout in milliseconds |

## Returns

[`Tool`](Interface.Tool.md)\<[`BashInput`](Interface.BashInput.md)\>
