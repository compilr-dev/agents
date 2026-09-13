---
title: "mcpToolsToTools"
parent: Functions
nav_order: 1
---


# Function: mcpToolsToTools()

```ts
function mcpToolsToTools(
   mcpTools, 
   client, 
   options?): Tool<object>[];
```

Defined in: mcp/tools.ts:129

Convert multiple MCP tools to our Tool format

## Parameters

| Parameter | Type |
| ------ | ------ |
| `mcpTools` | [`MCPToolDefinition`](Interface.MCPToolDefinition.md)[] |
| `client` | [`MCPClient`](Class.MCPClient.md) |
| `options` | [`MCPToolConversionOptions`](Interface.MCPToolConversionOptions.md) |

## Returns

[`Tool`](Interface.Tool.md)\<`object`\>[]
