---
title: "StateSerializer"
parent: Interfaces
nav_order: 1
---


# Interface: StateSerializer

Defined in: state/types.ts:169

Handles conversion between AgentState and string representation.

## Properties

### version

```ts
readonly version: string;
```

Defined in: state/types.ts:191

Version identifier for migration support

## Methods

### deserialize()

```ts
deserialize(data): AgentState;
```

Defined in: state/types.ts:179

Deserialize string back to agent state

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `data` | `string` |

#### Returns

[`AgentState`](Interface.AgentState.md)

#### Throws

StateError if data is invalid

### migrate()?

```ts
optional migrate(data, fromVersion): string;
```

Defined in: state/types.ts:196

Optional migration from older versions

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `data` | `string` |
| `fromVersion` | `string` |

#### Returns

`string`

### serialize()

```ts
serialize(state): string;
```

Defined in: state/types.ts:173

Serialize agent state to string

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `state` | [`AgentState`](Interface.AgentState.md) |

#### Returns

`string`

### validate()

```ts
validate(state): void;
```

Defined in: state/types.ts:186

Validate state before serialization.
Called by checkpointers before saving to prevent corrupted checkpoints.

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `state` | [`AgentState`](Interface.AgentState.md) |

#### Returns

`void`

#### Throws

StateError if state is invalid
