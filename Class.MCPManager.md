---
title: "MCPManager"
parent: Classes
nav_order: 1
---


# Class: MCPManager

Defined in: mcp/manager.ts:53

MCP Manager for managing multiple MCP server connections

## Example

```typescript
const manager = new MCPManager();

// Add servers
await manager.addServer({
  name: 'filesystem',
  transport: 'stdio',
  command: 'npx',
  args: ['-y', '@modelcontextprotocol/server-filesystem', '/tmp'],
});

// Discover and get tools
const tools = await manager.discoverTools();

// Use with agent
const agent = new Agent({
  provider: claude,
  tools: [...builtinTools, ...tools],
});

// Cleanup
await manager.disconnectAll();
```

## Constructors

### Constructor

```ts
new MCPManager(options?): MCPManager;
```

Defined in: mcp/manager.ts:60

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `options` | [`MCPManagerOptions`](Interface.MCPManagerOptions.md) |

#### Returns

`MCPManager`

## Methods

### addServer()

```ts
addServer(config): Promise<MCPClient>;
```

Defined in: mcp/manager.ts:83

Add an MCP server

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `config` | [`MCPServerConfig`](Interface.MCPServerConfig.md) | Server configuration |

#### Returns

`Promise`\<[`MCPClient`](Class.MCPClient.md)\>

The created MCPClient

#### Throws

MCPError if server with same name already exists

### connectAll()

```ts
connectAll(): Promise<void>;
```

Defined in: mcp/manager.ts:283

Connect all servers

#### Returns

`Promise`\<`void`\>

### disconnectAll()

```ts
disconnectAll(): Promise<void>;
```

Defined in: mcp/manager.ts:304

Disconnect all servers

#### Returns

`Promise`\<`void`\>

### discoverTools()

```ts
discoverTools(): Promise<Tool<object>[]>;
```

Defined in: mcp/manager.ts:183

Discover tools from all connected servers

#### Returns

`Promise`\<[`Tool`](Interface.Tool.md)\<`object`\>[]\>

Array of converted tools ready for registration

### discoverToolsFrom()

```ts
discoverToolsFrom(serverName): Promise<Tool<object>[]>;
```

Defined in: mcp/manager.ts:209

Discover tools from a specific server

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `serverName` | `string` |

#### Returns

`Promise`\<[`Tool`](Interface.Tool.md)\<`object`\>[]\>

### getServer()

```ts
getServer(name): MCPClient | undefined;
```

Defined in: mcp/manager.ts:153

Get an MCP client by name

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `name` | `string` |

#### Returns

[`MCPClient`](Class.MCPClient.md) \| `undefined`

### getServerNames()

```ts
getServerNames(): string[];
```

Defined in: mcp/manager.ts:167

Get all server names

#### Returns

`string`[]

### getServers()

```ts
getServers(): MCPClient[];
```

Defined in: mcp/manager.ts:160

Get all MCP clients

#### Returns

[`MCPClient`](Class.MCPClient.md)[]

### hasServer()

```ts
hasServer(name): boolean;
```

Defined in: mcp/manager.ts:174

Check if a server exists

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `name` | `string` |

#### Returns

`boolean`

### onEvent()

```ts
onEvent(handler): () => void;
```

Defined in: mcp/manager.ts:312

Register an event handler

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `handler` | [`MCPClientEventHandler`](TypeAlias.MCPClientEventHandler.md) |

#### Returns

() => `void`

### refreshTools()

```ts
refreshTools(serverName?): Promise<void>;
```

Defined in: mcp/manager.ts:236

Refresh tools from servers and update the tool registry

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `serverName?` | `string` | Optional server name to refresh. If not provided, refreshes all. |

#### Returns

`Promise`\<`void`\>

### removeServer()

```ts
removeServer(name): Promise<void>;
```

Defined in: mcp/manager.ts:125

Remove an MCP server

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `name` | `string` | Server name |

#### Returns

`Promise`\<`void`\>

#### Throws

MCPError if server not found

### setToolRegistry()

```ts
setToolRegistry(registry): void;
```

Defined in: mcp/manager.ts:72

Set a tool registry for automatic tool registration
When set, tools from MCP servers will be automatically registered

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `registry` | [`DefaultToolRegistry`](Class.DefaultToolRegistry.md) |

#### Returns

`void`
