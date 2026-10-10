---
title: "ToolRegistry"
parent: Interfaces
nav_order: 1
---


# Interface: ToolRegistry

Defined in: tools/types.ts:185

Tool registry for managing available tools

## Methods

### execute()

```ts
execute(
   name, 
   input, 
context?): Promise<ToolExecutionResult>;
```

Defined in: tools/types.ts:207

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
get(name): AnyTool | undefined;
```

Defined in: tools/types.ts:194

Get a tool by name

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `name` | `string` |

#### Returns

`AnyTool` \| `undefined`

### getDefinitions()

```ts
getDefinitions(): ToolDefinition[];
```

Defined in: tools/types.ts:199

Get all tool definitions (for sending to LLM)

#### Returns

`ToolDefinition`[]

### register()

```ts
register(tool): void;
```

Defined in: tools/types.ts:189

Register a tool

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `tool` | `AnyTool` |

#### Returns

`void`

### setFallbackHandler()

```ts
setFallbackHandler(handler): void;
```

Defined in: tools/types.ts:217

Set a fallback handler for tools not found in the primary registry.
Enables transparent routing to secondary registries (e.g., meta-tools).

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `handler` | [`ToolFallbackHandler`](TypeAlias.ToolFallbackHandler.md) \| `null` |

#### Returns

`void`
