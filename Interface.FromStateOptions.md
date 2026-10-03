---
title: "FromStateOptions"
parent: Interfaces
nav_order: 1
---


# Interface: FromStateOptions

Defined in: state/types.ts:371

Options for creating agent from exported state.

## Properties

### checkpointer?

```ts
optional checkpointer?: Checkpointer;
```

Defined in: state/types.ts:380

Optional checkpointer for subsequent saves

### onEvent?

```ts
optional onEvent?: (event) => void;
```

Defined in: state/types.ts:390

Event handler

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `event` | `unknown` |

#### Returns

`void`

### provider

```ts
provider: unknown;
```

Defined in: state/types.ts:375

LLM provider to use

### tools?

```ts
optional tools?: unknown[];
```

Defined in: state/types.ts:385

Override saved tools
