---
title: "MCPStdioOptions"
parent: Interfaces
nav_order: 1
---


# Interface: MCPStdioOptions

Defined in: mcp/types.ts:23

Options for connecting to an MCP server via stdio transport

## Properties

### args?

```ts
optional args?: string[];
```

Defined in: mcp/types.ts:27

Arguments to pass to the command

### command

```ts
command: string;
```

Defined in: mcp/types.ts:25

Command to spawn (e.g., 'npx', 'node', 'python')

### cwd?

```ts
optional cwd?: string;
```

Defined in: mcp/types.ts:31

Working directory for the spawned process

### env?

```ts
optional env?: Record<string, string>;
```

Defined in: mcp/types.ts:29

Environment variables for the spawned process
