---
title: "FileCheckpointer"
parent: Classes
nav_order: 1
---


# Class: FileCheckpointer

Defined in: state/checkpointer.ts:243

File-based checkpointer for simple persistence.
Stores each session as a separate JSON file.

## Implements

- [`Checkpointer`](Interface.Checkpointer.md)

## Constructors

### Constructor

```ts
new FileCheckpointer(baseDir, options?): FileCheckpointer;
```

Defined in: state/checkpointer.ts:248

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `baseDir` | `string` |
| `options?` | [`FileCheckpointerOptions`](Interface.FileCheckpointerOptions.md) |

#### Returns

`FileCheckpointer`

## Methods

### delete()

```ts
delete(sessionId): Promise<boolean>;
```

Defined in: state/checkpointer.ts:397

Delete a session

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `sessionId` | `string` |

#### Returns

`Promise`\<`boolean`\>

#### Implementation of

[`Checkpointer`](Interface.Checkpointer.md).[`delete`](Interface.Checkpointer.md#delete)

### exists()

```ts
exists(sessionId): Promise<boolean>;
```

Defined in: state/checkpointer.ts:432

Check if session exists

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `sessionId` | `string` |

#### Returns

`Promise`\<`boolean`\>

#### Implementation of

[`Checkpointer`](Interface.Checkpointer.md).[`exists`](Interface.Checkpointer.md#exists)

### getMetadata()

```ts
getMetadata(sessionId): Promise<SessionMetadata | null>;
```

Defined in: state/checkpointer.ts:446

Get session metadata

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `sessionId` | `string` |

#### Returns

`Promise`\<[`SessionMetadata`](Interface.SessionMetadata.md) \| `null`\>

#### Implementation of

[`Checkpointer`](Interface.Checkpointer.md).[`getMetadata`](Interface.Checkpointer.md#getmetadata)

### list()

```ts
list(options?): Promise<SessionInfo[]>;
```

Defined in: state/checkpointer.ts:343

List all sessions

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `options?` | [`ListSessionsOptions`](Interface.ListSessionsOptions.md) |

#### Returns

`Promise`\<[`SessionInfo`](Interface.SessionInfo.md)[]\>

#### Implementation of

[`Checkpointer`](Interface.Checkpointer.md).[`list`](Interface.Checkpointer.md#list)

### load()

```ts
load(sessionId): Promise<AgentState | null>;
```

Defined in: state/checkpointer.ts:323

Load state from file

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `sessionId` | `string` |

#### Returns

`Promise`\<[`AgentState`](Interface.AgentState.md) \| `null`\>

#### Implementation of

[`Checkpointer`](Interface.Checkpointer.md).[`load`](Interface.Checkpointer.md#load)

### save()

```ts
save(
   sessionId, 
   state, 
metadataOverrides?): Promise<void>;
```

Defined in: state/checkpointer.ts:288

Save state to file

Pre-validates state before saving to prevent corrupted checkpoints.
This catches issues like invalid data types that would fail on reload.

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `sessionId` | `string` |
| `state` | [`AgentState`](Interface.AgentState.md) |
| `metadataOverrides?` | `Partial`\<[`SessionMetadata`](Interface.SessionMetadata.md)\> |

#### Returns

`Promise`\<`void`\>

#### Implementation of

[`Checkpointer`](Interface.Checkpointer.md).[`save`](Interface.Checkpointer.md#save)
