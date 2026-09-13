---
title: "ProjectMemoryLoader"
parent: Classes
nav_order: 1
---


# Class: ProjectMemoryLoader

Defined in: memory/loader.ts:171

ProjectMemoryLoader discovers and loads project-specific instructions

## Constructors

### Constructor

```ts
new ProjectMemoryLoader(options?): ProjectMemoryLoader;
```

Defined in: memory/loader.ts:176

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `options` | [`ProjectMemoryOptions`](Interface.ProjectMemoryOptions.md) |

#### Returns

`ProjectMemoryLoader`

## Methods

### discover()

```ts
discover(rootDir): Promise<MemoryDiscoveryResult>;
```

Defined in: memory/loader.ts:331

Discover memory files without loading content

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `rootDir` | `string` | Starting directory for search |

#### Returns

`Promise`\<[`MemoryDiscoveryResult`](Interface.MemoryDiscoveryResult.md)\>

Discovery result with paths

### getOptions()

```ts
getOptions(): Required<ProjectMemoryOptions>;
```

Defined in: memory/loader.ts:486

Get the configured options

#### Returns

`Required`\<[`ProjectMemoryOptions`](Interface.ProjectMemoryOptions.md)\>

### getPatterns()

```ts
getPatterns(): FilePattern[];
```

Defined in: memory/loader.ts:479

Get the patterns being used

#### Returns

[`FilePattern`](Interface.FilePattern.md)[]

### load()

```ts
load(rootDir): Promise<ProjectMemory>;
```

Defined in: memory/loader.ts:236

Load project memory from a directory

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `rootDir` | `string` | Starting directory for search |

#### Returns

`Promise`\<[`ProjectMemory`](Interface.ProjectMemory.md)\>

Loaded project memory

### onEvent()

```ts
onEvent(handler): () => void;
```

Defined in: memory/loader.ts:458

Register an event handler

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `handler` | [`ProjectMemoryEventHandler`](TypeAlias.ProjectMemoryEventHandler.md) |

#### Returns

() => `void`
