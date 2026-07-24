---
title: "mcpToolToTool"
parent: Functions
nav_order: 1
---


# Function: mcpToolToTool()

```ts
function mcpToolToTool(
   mcpTool, 
   client, 
   options?): Tool;
```

Defined in: mcp/tools.ts:100

Convert a single MCP tool to our Tool format

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `mcpTool` | [`MCPToolDefinition`](Interface.MCPToolDefinition.md) | The MCP tool definition from the server |
| `client` | [`MCPClient`](Class.MCPClient.md) | The MCP client to use for calling the tool |
| `options` | [`MCPToolConversionOptions`](Interface.MCPToolConversionOptions.md) | Conversion options |

## Returns

[`Tool`](Interface.Tool.md)

A Tool that can be registered with the agent

## Example

```typescript
const tools = await client.listTools();
const convertedTools = tools.map(t => mcpToolToTool(t, client));
agent.toolRegistry.registerTools(convertedTools);
```
