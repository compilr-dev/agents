---
title: "MemoryCheckpointer"
parent: Classes
nav_order: 1
---


# Class: MemoryCheckpointer

Defined in: state/checkpointer.ts:116

In-memory checkpointer for development and testing.
State is lost when the process exits.

## Implements

- [`Checkpointer`](Interface.Checkpointer.md)

## Constructors

### Constructor

```ts
new MemoryCheckpointer(): MemoryCheckpointer;
```

#### Returns

`MemoryCheckpointer`

## Accessors

### size

#### Get Signature

```ts
get size(): number;
```

Defined in: state/checkpointer.ts:215

Get current session count

##### Returns

`number`

## Methods

### clear()

```ts
clear(): void;
```

Defined in: state/checkpointer.ts:208

Clear all sessions (useful for testing)

#### Returns

`void`

### delete()

```ts
delete(sessionId): Promise<boolean>;
```

Defined in: state/checkpointer.ts:182

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

Defined in: state/checkpointer.ts:190

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

Defined in: state/checkpointer.ts:198

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

Defined in: state/checkpointer.ts:155

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

Defined in: state/checkpointer.ts:145

Load state from memory

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

Defined in: state/checkpointer.ts:125

Save state to memory

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
