---
title: "ObservationMasker"
parent: Classes
nav_order: 1
---


# Class: ObservationMasker

Defined in: context/observation-masker.ts:99

## Constructors

### Constructor

```ts
new ObservationMasker(config?): ObservationMasker;
```

Defined in: context/observation-masker.ts:106

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `config?` | `Partial`\<[`ObservationMaskConfig`](Interface.ObservationMaskConfig.md)\> |

#### Returns

`ObservationMasker`

## Methods

### getConfig()

```ts
getConfig(): ObservationMaskConfig;
```

Defined in: context/observation-masker.ts:281

Get current configuration (for testing/inspection).

#### Returns

[`ObservationMaskConfig`](Interface.ObservationMaskConfig.md)

### getStats()

```ts
getStats(): ObservationMaskStats;
```

Defined in: context/observation-masker.ts:263

#### Returns

[`ObservationMaskStats`](Interface.ObservationMaskStats.md)

### maskHistory()

```ts
maskHistory(messages, currentTurn): MaskResult;
```

Defined in: context/observation-masker.ts:166

Mask old tool results, images, and compact old tool_use inputs in-place.
- tool_result: replaces content with compact mask text (Phase 1)
- image: replaces with text placeholder after maskAfterTurns (Phase 2)
- tool_use input: strips large fields, keeping only identifying fields (Phase 1b)

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `messages` | [`Message`](Interface.Message.md)[] |
| `currentTurn` | `number` |

#### Returns

[`MaskResult`](Interface.MaskResult.md)

### reset()

```ts
reset(): void;
```

Defined in: context/observation-masker.ts:273

Reset all state (stamps and stats). Used when clearing history.

#### Returns

`void`

### stamp()

```ts
stamp(
   toolUseId, 
   toolName, 
   input, 
   contentLength, 
   turn): void;
```

Defined in: context/observation-masker.ts:118

Register a tool result with its turn number and input context.
Called immediately after a tool result is added to the messages array.

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `toolUseId` | `string` |
| `toolName` | `string` |
| `input` | `Record`\<`string`, `unknown`\> |
| `contentLength` | `number` |
| `turn` | `number` |

#### Returns

`void`

### stampImages()

```ts
stampImages(messages, turn): void;
```

Defined in: context/observation-masker.ts:141

Stamp all image blocks in a message array with the current turn.
Call this after adding user messages that may contain images.

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `messages` | [`Message`](Interface.Message.md)[] |
| `turn` | `number` |

#### Returns

`void`
