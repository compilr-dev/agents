---
title: "DeadMessagePruner"
parent: Classes
nav_order: 1
---


# Class: DeadMessagePruner

Defined in: context/dead-message-pruner.ts:82

## Constructors

### Constructor

```ts
new DeadMessagePruner(config?): DeadMessagePruner;
```

Defined in: context/dead-message-pruner.ts:92

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `config?` | `Partial`\<[`PruneConfig`](Interface.PruneConfig.md)\> |

#### Returns

`DeadMessagePruner`

## Methods

### getConfig()

```ts
getConfig(): PruneConfig;
```

Defined in: context/dead-message-pruner.ts:208

Get current configuration (for testing/inspection).

#### Returns

[`PruneConfig`](Interface.PruneConfig.md)

### getStats()

```ts
getStats(): PruneStats;
```

Defined in: context/dead-message-pruner.ts:193

#### Returns

[`PruneStats`](Interface.PruneStats.md)

### prune()

```ts
prune(messages, currentTurn): PruneResult;
```

Defined in: context/dead-message-pruner.ts:127

Prune dead messages in-place. Replaces content of dead tool_result
blocks with short placeholders and clears corresponding tool_use input.

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `messages` | [`Message`](Interface.Message.md)[] |
| `currentTurn` | `number` |

#### Returns

[`PruneResult`](Interface.PruneResult.md)

### reset()

```ts
reset(): void;
```

Defined in: context/dead-message-pruner.ts:200

Reset all state (stamps and stats). Used when clearing history.

#### Returns

`void`

### stamp()

```ts
stamp(
   toolUseId, 
   toolName, 
   input, 
   isError, 
   turn): void;
```

Defined in: context/dead-message-pruner.ts:104

Register a tool result for pruning analysis.
Called at the same point as ObservationMasker.stamp().

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `toolUseId` | `string` |
| `toolName` | `string` |
| `input` | `Record`\<`string`, `unknown`\> |
| `isError` | `boolean` |
| `turn` | `number` |

#### Returns

`void`
