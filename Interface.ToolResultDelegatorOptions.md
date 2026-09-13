---
title: "ToolResultDelegatorOptions"
parent: Interfaces
nav_order: 1
---


# Interface: ToolResultDelegatorOptions

Defined in: context/tool-result-delegator.ts:19

Options for creating a ToolResultDelegator.

## Properties

### config?

```ts
optional config?: Partial<DelegationConfig>;
```

Defined in: context/tool-result-delegator.ts:24

Delegation configuration (merged with defaults)

### onEvent?

```ts
optional onEvent?: (event) => void;
```

Defined in: context/tool-result-delegator.ts:27

Event callback for delegation lifecycle events

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `event` | [`DelegationEvent`](TypeAlias.DelegationEvent.md) |

#### Returns

`void`

### provider

```ts
provider: LLMProvider;
```

Defined in: context/tool-result-delegator.ts:21

LLM provider for summarization (small/medium tier preferred)
