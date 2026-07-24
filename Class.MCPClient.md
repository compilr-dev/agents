---
title: "MCPClient"
parent: Classes
nav_order: 1
---


# Class: MCPClient

Defined in: mcp/client.ts:110

MCP Client for connecting to a single MCP server

## Example

```typescript
const client = new MCPClient({
  name: 'filesystem',
  transport: 'stdio',
  stdio: {
    command: 'npx',
    args: ['-y', '@modelcontextprotocol/server-filesystem', '/tmp'],
  },
});

await client.connect();
const tools = await client.listTools();
const result = await client.callTool('read_file', { path: '/tmp/test.txt' });
await client.disconnect();
```

## Constructors

### Constructor

```ts
new MCPClient(config): MCPClient;
```

Defined in: mcp/client.ts:119

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `config` | [`MCPClientConfig`](Interface.MCPClientConfig.md) |

#### Returns

`MCPClient`

## Properties

### name

```ts
readonly name: string;
```

Defined in: mcp/client.ts:111

## Accessors

### isConnected

#### Get Signature

```ts
get isConnected(): boolean;
```

Defined in: mcp/client.ts:150

Whether the client is connected

##### Returns

`boolean`

### status

#### Get Signature

```ts
get status(): MCPConnectionStatus;
```

Defined in: mcp/client.ts:143

Current connection status

##### Returns

[`MCPConnectionStatus`](TypeAlias.MCPConnectionStatus.md)

## Methods

### callTool()

```ts
callTool(toolName, args?): Promise<MCPToolResult>;
```

Defined in: mcp/client.ts:288

Call a tool on the server

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `toolName` | `string` | Name of the tool to call |
| `args?` | `Record`\<`string`, `unknown`\> | Arguments to pass to the tool |

#### Returns

`Promise`\<[`MCPToolResult`](Interface.MCPToolResult.md)\>

#### Throws

MCPError if not connected, tool not found, or execution fails

### connect()

```ts
connect(): Promise<void>;
```

Defined in: mcp/client.ts:158

Connect to the MCP server

#### Returns

`Promise`\<`void`\>

#### Throws

MCPError if connection fails

### disconnect()

```ts
disconnect(): Promise<void>;
```

Defined in: mcp/client.ts:236

Disconnect from the MCP server

#### Returns

`Promise`\<`void`\>

### listTools()

```ts
listTools(): Promise<MCPToolDefinition[]>;
```

Defined in: mcp/client.ts:260

List available tools from the server

#### Returns

`Promise`\<[`MCPToolDefinition`](Interface.MCPToolDefinition.md)[]\>

#### Throws

MCPError if not connected or listing fails

### onDisconnect()

```ts
onDisconnect(callback): () => void;
```

Defined in: mcp/client.ts:358

Convenience method to listen for disconnect

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `callback` | () => `void` |

#### Returns

() => `void`

### onError()

```ts
onError(callback): () => void;
```

Defined in: mcp/client.ts:347

Convenience method to listen for errors

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `callback` | (`error`) => `void` |

#### Returns

() => `void`

### onEvent()

```ts
onEvent(handler): () => void;
```

Defined in: mcp/client.ts:323

Register an event handler

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `handler` | [`MCPClientEventHandler`](TypeAlias.MCPClientEventHandler.md) |

#### Returns

() => `void`

### onToolsChanged()

```ts
onToolsChanged(callback): () => void;
```

Defined in: mcp/client.ts:331

Convenience method to listen for tools changed events

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `callback` | (`tools`) => `void` |

#### Returns

() => `void`
