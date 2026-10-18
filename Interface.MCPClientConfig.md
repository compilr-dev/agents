---
title: "MCPClientConfig"
parent: Interfaces
nav_order: 1
---


# Interface: MCPClientConfig

Defined in: mcp/types.ts:47

Configuration for an MCP client

## Properties

### clientName?

```ts
optional clientName?: string;
```

Defined in: mcp/types.ts:59

Client name reported to server (default: '@compilr-dev/agents')

### clientVersion?

```ts
optional clientVersion?: string;
```

Defined in: mcp/types.ts:61

Client version reported to server (default: '1.0.0')

### http?

```ts
optional http?: MCPHttpOptions;
```

Defined in: mcp/types.ts:55

HTTP transport options (required if transport is 'http')

### name

```ts
name: string;
```

Defined in: mcp/types.ts:49

Unique name/identifier for this server connection

### stdio?

```ts
optional stdio?: MCPStdioOptions;
```

Defined in: mcp/types.ts:53

Stdio transport options (required if transport is 'stdio')

### timeout?

```ts
optional timeout?: number;
```

Defined in: mcp/types.ts:57

Connection timeout in milliseconds (default: 30000)

### transport

```ts
transport: MCPTransport;
```

Defined in: mcp/types.ts:51

Transport type
