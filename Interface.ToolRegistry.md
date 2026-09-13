---
title: "ToolRegistry"
parent: Interfaces
nav_order: 1
---


# Interface: ToolRegistry

Defined in: tools/types.ts:169

Tool registry for managing available tools

## Methods

### execute()

```ts
execute(
   name, 
   input, 
context?): Promise<ToolExecutionResult>;
```

Defined in: tools/types.ts:191

Execute a tool by name with given input

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `name` | `string` | Tool name |
| `input` | `Record`\<`string`, `unknown`\> | Tool input parameters |
| `context?` | `ToolExecutionContext` | Optional execution context for streaming |

#### Returns

`Promise`\<[`ToolExecutionResult`](Interface.ToolExecutionResult.md)\>

### get()

```ts
get(name): Tool<object> | undefined;
```

Defined in: tools/types.ts:178

Get a tool by name

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `name` | `string` |

#### Returns

[`Tool`](Interface.Tool.md)\<`object`\> \| `undefined`

### getDefinitions()

```ts
getDefinitions(): ToolDefinition[];
```

Defined in: tools/types.ts:183

Get all tool definitions (for sending to LLM)

#### Returns

`ToolDefinition`[]

### register()

```ts
register(tool): void;
```

Defined in: tools/types.ts:173

Register a tool

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `tool` | [`Tool`](Interface.Tool.md) |

#### Returns

`void`

### setFallbackHandler()

```ts
setFallbackHandler(handler): void;
```

Defined in: tools/types.ts:201

Set a fallback handler for tools not found in the primary registry.
Enables transparent routing to secondary registries (e.g., meta-tools).

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `handler` | [`ToolFallbackHandler`](TypeAlias.ToolFallbackHandler.md) \| `null` |

#### Returns

`void`
