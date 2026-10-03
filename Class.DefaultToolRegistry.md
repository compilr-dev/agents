---
title: "DefaultToolRegistry"
parent: Classes
nav_order: 1
---


# Class: DefaultToolRegistry

Defined in: tools/registry.ts:49

Default implementation of ToolRegistry

## Implements

- [`ToolRegistry`](Interface.ToolRegistry.md)

## Constructors

### Constructor

```ts
new DefaultToolRegistry(options?): DefaultToolRegistry;
```

Defined in: tools/registry.ts:55

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `options?` | [`ToolRegistryOptions`](Interface.ToolRegistryOptions.md) |

#### Returns

`DefaultToolRegistry`

## Accessors

### size

#### Get Signature

```ts
get size(): number;
```

Defined in: tools/registry.ts:126

Get the number of registered tools

##### Returns

`number`

## Methods

### clear()

```ts
clear(): void;
```

Defined in: tools/registry.ts:238

Clear all registered tools

#### Returns

`void`

### execute()

```ts
execute(
   name, 
   input, 
   contextOrTimeout?, 
timeoutMs?): Promise<ToolExecutionResult>;
```

Defined in: tools/registry.ts:138

Execute a tool by name with given input

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `name` | `string` | Tool name |
| `input` | `Record`\<`string`, `unknown`\> | Tool input parameters |
| `contextOrTimeout?` | `number` \| `ToolExecutionContext` | Optional execution context or timeout override |
| `timeoutMs?` | `number` | Optional timeout override (uses default if not provided) |

#### Returns

`Promise`\<[`ToolExecutionResult`](Interface.ToolExecutionResult.md)\>

#### Implementation of

[`ToolRegistry`](Interface.ToolRegistry.md).[`execute`](Interface.ToolRegistry.md#execute)

### get()

```ts
get(name): AnyTool | undefined;
```

Defined in: tools/registry.ts:98

Get a tool by name

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `name` | `string` |

#### Returns

`AnyTool` \| `undefined`

#### Implementation of

[`ToolRegistry`](Interface.ToolRegistry.md).[`get`](Interface.ToolRegistry.md#get)

### getDefinitions()

```ts
getDefinitions(): ToolDefinition[];
```

Defined in: tools/registry.ts:119

Get all tool definitions (for sending to LLM)

#### Returns

`ToolDefinition`[]

#### Implementation of

[`ToolRegistry`](Interface.ToolRegistry.md).[`getDefinitions`](Interface.ToolRegistry.md#getdefinitions)

### getNames()

```ts
getNames(): string[];
```

Defined in: tools/registry.ts:112

Get all registered tool names

#### Returns

`string`[]

### getOptions()

```ts
getOptions(): ToolRegistryOptions;
```

Defined in: tools/registry.ts:245

Get the registry options (for inheritance by sub-agents)

#### Returns

[`ToolRegistryOptions`](Interface.ToolRegistryOptions.md)

### has()

```ts
has(name): boolean;
```

Defined in: tools/registry.ts:105

Check if a tool is registered

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `name` | `string` |

#### Returns

`boolean`

### register()

```ts
register(tool): void;
```

Defined in: tools/registry.ts:72

Register a tool

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `tool` | `AnyTool` |

#### Returns

`void`

#### Implementation of

[`ToolRegistry`](Interface.ToolRegistry.md).[`register`](Interface.ToolRegistry.md#register)

### registerAll()

```ts
registerAll(tools): void;
```

Defined in: tools/registry.ts:82

Register multiple tools at once

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `tools` | `AnyTool`[] |

#### Returns

`void`

### setFallbackHandler()

```ts
setFallbackHandler(handler): void;
```

Defined in: tools/registry.ts:65

Set a fallback handler for tools not found in the primary registry.
Enables transparent routing to secondary registries (e.g., meta-tools).

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `handler` | [`ToolFallbackHandler`](TypeAlias.ToolFallbackHandler.md) \| `null` |

#### Returns

`void`

#### Implementation of

[`ToolRegistry`](Interface.ToolRegistry.md).[`setFallbackHandler`](Interface.ToolRegistry.md#setfallbackhandler)

### unregister()

```ts
unregister(name): boolean;
```

Defined in: tools/registry.ts:91

Unregister a tool by name

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `name` | `string` |

#### Returns

`boolean`
