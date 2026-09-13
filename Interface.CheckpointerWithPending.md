---
title: "CheckpointerWithPending"
parent: Interfaces
nav_order: 1
---


# Interface: CheckpointerWithPending

Defined in: state/types.ts:317

Extended checkpointer with fault tolerance support.
Tracks pending writes for recovery from mid-step failures.

## Extends

- [`Checkpointer`](Interface.Checkpointer.md)

## Methods

### clearPending()

```ts
clearPending(sessionId): Promise<void>;
```

Defined in: state/types.ts:331

Clear pending writes (called after step completion)

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `sessionId` | `string` |

#### Returns

`Promise`\<`void`\>

### delete()

```ts
delete(sessionId): Promise<boolean>;
```

Defined in: state/types.ts:264

Delete a saved session

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `sessionId` | `string` | Session to delete |

#### Returns

`Promise`\<`boolean`\>

true if deleted, false if not found

#### Inherited from

[`Checkpointer`](Interface.Checkpointer.md).[`delete`](Interface.Checkpointer.md#delete)

### exists()

```ts
exists(sessionId): Promise<boolean>;
```

Defined in: state/types.ts:270

Check if a session exists

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `sessionId` | `string` | Session to check |

#### Returns

`Promise`\<`boolean`\>

#### Inherited from

[`Checkpointer`](Interface.Checkpointer.md).[`exists`](Interface.Checkpointer.md#exists)

### getMetadata()

```ts
getMetadata(sessionId): Promise<SessionMetadata | null>;
```

Defined in: state/types.ts:276

Get session metadata without loading full state

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `sessionId` | `string` | Session to query |

#### Returns

`Promise`\<[`SessionMetadata`](Interface.SessionMetadata.md) \| `null`\>

#### Inherited from

[`Checkpointer`](Interface.Checkpointer.md).[`getMetadata`](Interface.Checkpointer.md#getmetadata)

### list()

```ts
list(options?): Promise<SessionInfo[]>;
```

Defined in: state/types.ts:257

List all saved sessions

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `options?` | [`ListSessionsOptions`](Interface.ListSessionsOptions.md) | Optional filtering/sorting options |

#### Returns

`Promise`\<[`SessionInfo`](Interface.SessionInfo.md)[]\>

Array of session info (without full state)

#### Inherited from

[`Checkpointer`](Interface.Checkpointer.md).[`list`](Interface.Checkpointer.md#list)

### load()

```ts
load(sessionId): Promise<AgentState | null>;
```

Defined in: state/types.ts:250

Load agent state from storage

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `sessionId` | `string` | Session to load |

#### Returns

`Promise`\<[`AgentState`](Interface.AgentState.md) \| `null`\>

AgentState if found, null if not exists

#### Inherited from

[`Checkpointer`](Interface.Checkpointer.md).[`load`](Interface.Checkpointer.md#load)

### loadPending()

```ts
loadPending(sessionId): Promise<PendingWrite[]>;
```

Defined in: state/types.ts:326

Load pending writes for a session

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `sessionId` | `string` |

#### Returns

`Promise`\<[`PendingWrite`](Interface.PendingWrite.md)[]\>

### save()

```ts
save(
   sessionId, 
   state, 
metadata?): Promise<void>;
```

Defined in: state/types.ts:243

Save agent state to storage

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `sessionId` | `string` | Unique session identifier |
| `state` | [`AgentState`](Interface.AgentState.md) | Complete agent state to save |
| `metadata?` | `Partial`\<[`SessionMetadata`](Interface.SessionMetadata.md)\> | Optional metadata overrides |

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`Checkpointer`](Interface.Checkpointer.md).[`save`](Interface.Checkpointer.md#save)

### savePending()

```ts
savePending(sessionId, writes): Promise<void>;
```

Defined in: state/types.ts:321

Save pending writes (incomplete tool executions)

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `sessionId` | `string` |
| `writes` | [`PendingWrite`](Interface.PendingWrite.md)[] |

#### Returns

`Promise`\<`void`\>
