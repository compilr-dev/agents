---
title: "HookEvent"
parent: Interfaces
nav_order: 1
---


# Interface: HookEvent

Defined in: hooks/types.ts:455

Hook execution event payload

## Properties

### durationMs?

```ts
optional durationMs?: number;
```

Defined in: hooks/types.ts:460

### error?

```ts
optional error?: Error;
```

Defined in: hooks/types.ts:461

### hookId?

```ts
optional hookId?: string;
```

Defined in: hooks/types.ts:458

### hookName?

```ts
optional hookName?: string;
```

Defined in: hooks/types.ts:459

### hookType

```ts
hookType: keyof HooksConfig;
```

Defined in: hooks/types.ts:457

### type

```ts
type: HookEventType;
```

Defined in: hooks/types.ts:456
