---
title: "ToolDefinition"
parent: Interfaces
nav_order: 1
---


# Interface: ToolDefinition

Defined in: providers/types.ts:236

Tool definition for the LLM

## Properties

### description

```ts
description: string;
```

Defined in: providers/types.ts:238

### inputSchema

```ts
inputSchema: {
  properties: Record<string, unknown>;
  required?: string[];
  type: "object";
};
```

Defined in: providers/types.ts:239

#### properties

```ts
properties: Record<string, unknown>;
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

Defined in: providers/types.ts:237
