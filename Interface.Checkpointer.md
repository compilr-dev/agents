---
title: "Checkpointer"
parent: Interfaces
nav_order: 1
---


# Interface: Checkpointer

Defined in: state/types.ts:236

Core persistence interface. Implementations handle actual storage.

## Extended by

- [`CheckpointerWithPending`](Interface.CheckpointerWithPending.md)

## Methods

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
