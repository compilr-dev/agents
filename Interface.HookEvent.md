---
title: "HookEvent"
parent: Interfaces
nav_order: 1
---


# Interface: HookEvent

Defined in: hooks/types.ts:470

Hook execution event payload

## Properties

### durationMs?

```ts
optional durationMs?: number;
```

Defined in: hooks/types.ts:475

### error?

```ts
optional error?: Error;
```

Defined in: hooks/types.ts:476

### hookId?

```ts
optional hookId?: string;
```

Defined in: hooks/types.ts:473

### hookName?

```ts
optional hookName?: string;
```

Defined in: hooks/types.ts:474

### hookType

```ts
hookType: keyof HooksConfig;
```

Defined in: hooks/types.ts:472

### type

```ts
type: HookEventType;
```

Defined in: hooks/types.ts:471
