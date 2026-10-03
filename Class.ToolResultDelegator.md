---
title: "ToolResultDelegator"
parent: Classes
nav_order: 1
---


# Class: ToolResultDelegator

Defined in: context/tool-result-delegator.ts:54

Core class that creates an AfterToolHook for auto-delegating large tool results.

## Constructors

### Constructor

```ts
new ToolResultDelegator(options): ToolResultDelegator;
```

Defined in: context/tool-result-delegator.ts:60

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `options` | [`ToolResultDelegatorOptions`](Interface.ToolResultDelegatorOptions.md) |

#### Returns

`ToolResultDelegator`

## Methods

### createHook()

```ts
createHook(): AfterToolHook;
```

Defined in: context/tool-result-delegator.ts:73

Returns an AfterToolHook to register with HooksManager.

#### Returns

[`AfterToolHook`](TypeAlias.AfterToolHook.md)

### getStore()

```ts
getStore(): DelegatedResultStore;
```

Defined in: context/tool-result-delegator.ts:219

Access the store (needed by recall_full_result tool).

#### Returns

[`DelegatedResultStore`](Class.DelegatedResultStore.md)
