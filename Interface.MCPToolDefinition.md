---
title: "MCPToolDefinition"
parent: Interfaces
nav_order: 1
---


# Interface: MCPToolDefinition

Defined in: mcp/types.ts:98

MCP tool definition from the server
Based on MCP specification's Tool type

## Properties

### description?

```ts
optional description?: string;
```

Defined in: mcp/types.ts:102

Human-readable description

### inputSchema

```ts
inputSchema: {
[key: string]: unknown;
  additionalProperties?: boolean;
  properties?: Record<string, unknown>;
  required?: string[];
  type: "object";
};
```

Defined in: mcp/types.ts:104

JSON Schema for tool input

#### Index Signature

```ts
[key: string]: unknown
```

#### additionalProperties?

```ts
optional additionalProperties?: boolean;
```

#### properties?

```ts
optional properties?: Record<string, unknown>;
```

#### required?

```ts
optional required?: string[];
```

#### type

```ts
type: "object";
```

### name

```ts
name: string;
```

Defined in: mcp/types.ts:100

Tool name (unique identifier)
