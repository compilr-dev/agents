---
title: "JsonSerializer"
parent: Classes
nav_order: 1
---


# Class: JsonSerializer

Defined in: state/serializer.ts:15

JSON-based state serializer.
Handles standard JSON serialization with validation.

## Implements

- [`StateSerializer`](Interface.StateSerializer.md)

## Constructors

### Constructor

```ts
new JsonSerializer(): JsonSerializer;
```

#### Returns

`JsonSerializer`

## Properties

### version

```ts
readonly version: "1.0" = '1.0';
```

Defined in: state/serializer.ts:16

Version identifier for migration support

#### Implementation of

[`StateSerializer`](Interface.StateSerializer.md).[`version`](Interface.StateSerializer.md#version)

## Methods

### deserialize()

```ts
deserialize(data): AgentState;
```

Defined in: state/serializer.ts:35

Deserialize JSON string to agent state

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `data` | `string` |

#### Returns

[`AgentState`](Interface.AgentState.md)

#### Implementation of

[`StateSerializer`](Interface.StateSerializer.md).[`deserialize`](Interface.StateSerializer.md#deserialize)

### migrate()

```ts
migrate(data, fromVersion): string;
```

Defined in: state/serializer.ts:122

Migrate from older versions (currently no-op for v1)

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `data` | `string` |
| `fromVersion` | `string` |

#### Returns

`string`

#### Implementation of

[`StateSerializer`](Interface.StateSerializer.md).[`migrate`](Interface.StateSerializer.md#migrate)

### serialize()

```ts
serialize(state): string;
```

Defined in: state/serializer.ts:21

Serialize agent state to JSON string

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

Defined in: state/serializer.ts:63

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
