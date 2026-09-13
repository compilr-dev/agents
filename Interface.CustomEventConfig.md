---
title: "CustomEventConfig"
parent: Interfaces
nav_order: 1
---


# Interface: CustomEventConfig

Defined in: agent.ts:167

Custom event configuration

## Properties

### data

```ts
data: unknown;
```

Defined in: agent.ts:176

Event data payload

### metadata?

```ts
optional metadata?: Record<string, unknown>;
```

Defined in: agent.ts:181

Optional metadata (preserved through the event pipeline)

### name

```ts
name: string;
```

Defined in: agent.ts:171

Event name (used for filtering/routing)
