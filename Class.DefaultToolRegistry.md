---
title: "DefaultToolRegistry"
parent: Classes
nav_order: 1
---


# Class: DefaultToolRegistry

Defined in: tools/registry.ts:48

Default implementation of ToolRegistry

## Implements

- [`ToolRegistry`](Interface.ToolRegistry.md)

## Constructors

### Constructor

```ts
new DefaultToolRegistry(options?): DefaultToolRegistry;
```

Defined in: tools/registry.ts:54

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

Defined in: tools/registry.ts:125

Get the number of registered tools

##### Returns

`number`

## Methods

### clear()

```ts
clear(): void;
```

Defined in: tools/registry.ts:232

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

Defined in: tools/registry.ts:137

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
get(name): Tool<object> | undefined;
```

Defined in: tools/registry.ts:97

Get a tool by name

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `name` | `string` |

#### Returns

[`Tool`](Interface.Tool.md)\<`object`\> \| `undefined`

#### Implementation of

[`ToolRegistry`](Interface.ToolRegistry.md).[`get`](Interface.ToolRegistry.md#get)

### getDefinitions()

```ts
getDefinitions(): ToolDefinition[];
```

Defined in: tools/registry.ts:118

Get all tool definitions (for sending to LLM)

#### Returns

`ToolDefinition`[]

#### Implementation of

[`ToolRegistry`](Interface.ToolRegistry.md).[`getDefinitions`](Interface.ToolRegistry.md#getdefinitions)

### getNames()

```ts
getNames(): string[];
```

Defined in: tools/registry.ts:111

Get all registered tool names

#### Returns

`string`[]

### getOptions()

```ts
getOptions(): ToolRegistryOptions;
```

Defined in: tools/registry.ts:239

Get the registry options (for inheritance by sub-agents)

#### Returns

[`ToolRegistryOptions`](Interface.ToolRegistryOptions.md)

### has()

```ts
has(name): boolean;
```

Defined in: tools/registry.ts:104

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

Defined in: tools/registry.ts:71

Register a tool

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `tool` | [`Tool`](Interface.Tool.md) |

#### Returns

`void`

#### Implementation of

[`ToolRegistry`](Interface.ToolRegistry.md).[`register`](Interface.ToolRegistry.md#register)

### registerAll()

```ts
registerAll(tools): void;
```

Defined in: tools/registry.ts:81

Register multiple tools at once

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `tools` | [`Tool`](Interface.Tool.md)\<`object`\>[] |

#### Returns

`void`

### setFallbackHandler()

```ts
setFallbackHandler(handler): void;
```

Defined in: tools/registry.ts:64

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

Defined in: tools/registry.ts:90

Unregister a tool by name

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `name` | `string` |

#### Returns

`boolean`
