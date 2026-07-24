---
title: "RecallResultToolOptions"
parent: Interfaces
nav_order: 1
---


# Interface: RecallResultToolOptions

Defined in: tools/builtin/recall-result.ts:24

Options for creating the recall_full_result tool.

## Properties

### onEvent?

```ts
optional onEvent?: (event) => void;
```

Defined in: tools/builtin/recall-result.ts:29

Optional event callback for recall events

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `event` | [`DelegationEvent`](TypeAlias.DelegationEvent.md) |

#### Returns

`void`

### store

```ts
store: DelegatedResultStore;
```

Defined in: tools/builtin/recall-result.ts:26

The delegation store to retrieve results from
