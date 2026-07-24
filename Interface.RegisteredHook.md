---
title: "RegisteredHook"
parent: Interfaces
nav_order: 1
---


# Interface: RegisteredHook\<T\>

Defined in: hooks/types.ts:405

Internal representation of a registered hook

## Type Parameters

| Type Parameter |
| ------ |
| `T` |

## Properties

### hook

```ts
hook: T;
```

Defined in: hooks/types.ts:414

The hook function

### id

```ts
id: string;
```

Defined in: hooks/types.ts:409

Unique ID for this hook registration

### name?

```ts
optional name?: string;
```

Defined in: hooks/types.ts:419

Optional name for debugging

### priority?

```ts
optional priority?: number;
```

Defined in: hooks/types.ts:424

Priority (lower = runs first, default: 0)
