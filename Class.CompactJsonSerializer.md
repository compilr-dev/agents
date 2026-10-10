---
title: "CompactJsonSerializer"
parent: Classes
nav_order: 1
---


# Class: CompactJsonSerializer

Defined in: state/serializer.ts:139

Compact JSON serializer (no pretty printing).
Useful for storage-constrained environments.

## Implements

- [`StateSerializer`](Interface.StateSerializer.md)

## Constructors

### Constructor

```ts
new CompactJsonSerializer(): CompactJsonSerializer;
```

#### Returns

`CompactJsonSerializer`

## Properties

### version

```ts
readonly version: "1.0" = '1.0';
```

Defined in: state/serializer.ts:140

Version identifier for migration support

#### Implementation of

[`StateSerializer`](Interface.StateSerializer.md).[`version`](Interface.StateSerializer.md#version)

## Methods

### deserialize()

```ts
deserialize(data): AgentState;
```

Defined in: state/serializer.ts:153

Deserialize string back to agent state

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `data` | `string` |

#### Returns

[`AgentState`](Interface.AgentState.md)

#### Throws

StateError if data is invalid

#### Implementation of

[`StateSerializer`](Interface.StateSerializer.md).[`deserialize`](Interface.StateSerializer.md#deserialize)

### serialize()

```ts
serialize(state): string;
```

Defined in: state/serializer.ts:142

Serialize agent state to string

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `state` | [`AgentState`](Interface.AgentState.md) |

#### Returns

`string`

#### Implementation of

[`StateSerializer`](Interface.StateSerializer.md).[`serialize`](Interface.StateSerializer.md#serialize)

### validate()

```ts
validate(state): void;
```

Defined in: state/serializer.ts:181

Validate state before serialization (public interface method).
This is called by checkpointers before saving to prevent corrupted checkpoints.

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `state` | [`AgentState`](Interface.AgentState.md) |

#### Returns

`void`

#### Throws

StateError if state is invalid

#### Implementation of

[`StateSerializer`](Interface.StateSerializer.md).[`validate`](Interface.StateSerializer.md#validate)
