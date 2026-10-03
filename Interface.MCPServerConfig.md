---
title: "MCPServerConfig"
parent: Interfaces
nav_order: 1
---


# Interface: MCPServerConfig

Defined in: mcp/types.ts:68

Simplified configuration for quick server setup
Allows shorthand notation for common configurations

## Properties

### args?

```ts
optional args?: string[];
```

Defined in: mcp/types.ts:78

Command arguments

### command?

```ts
optional command?: string;
```

Defined in: mcp/types.ts:76

Command to spawn

### cwd?

```ts
optional cwd?: string;
```

Defined in: mcp/types.ts:82

Working directory

### env?

```ts
optional env?: Record<string, string>;
```

Defined in: mcp/types.ts:80

Environment variables

### headers?

```ts
optional headers?: Record<string, string>;
```

Defined in: mcp/types.ts:88

Custom headers

### name

```ts
name: string;
```

Defined in: mcp/types.ts:70

Unique name/identifier for this server

### timeout?

```ts
optional timeout?: number;
```

Defined in: mcp/types.ts:91

Connection timeout in milliseconds

### transport

```ts
transport: MCPTransport;
```

Defined in: mcp/types.ts:72

Transport type

### url?

```ts
optional url?: string;
```

Defined in: mcp/types.ts:86

Server URL
