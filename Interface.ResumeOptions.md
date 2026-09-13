---
title: "ResumeOptions"
parent: Interfaces
nav_order: 1
---


# Interface: ResumeOptions

Defined in: state/types.ts:341

Options for resuming an agent from a checkpoint.

## Properties

### checkpointer

```ts
checkpointer: Checkpointer;
```

Defined in: state/types.ts:350

Checkpointer to load from

### onEvent?

```ts
optional onEvent?: (event) => void;
```

Defined in: state/types.ts:365

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

Defined in: state/types.ts:345

LLM provider to use

### systemPrompt?

```ts
optional systemPrompt?: string;
```

Defined in: state/types.ts:355

Override saved system prompt

### tools?

```ts
optional tools?: unknown[];
```

Defined in: state/types.ts:360

Override saved tools
