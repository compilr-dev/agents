---
title: "GuardrailManagerOptions"
parent: Interfaces
nav_order: 1
---


# Interface: GuardrailManagerOptions

Defined in: guardrails/types.ts:161

Configuration for the GuardrailManager

## Properties

### custom?

```ts
optional custom?: GuardrailInput[];
```

Defined in: guardrails/types.ts:170

Custom guardrails to add

### enabled?

```ts
optional enabled?: boolean;
```

Defined in: guardrails/types.ts:165

Enable guardrails (default: true)

### includeDefaults?

```ts
optional includeDefaults?: boolean;
```

Defined in: guardrails/types.ts:175

Include built-in guardrails (default: true)

### onTriggered?

```ts
optional onTriggered?: GuardrailTriggeredHandler;
```

Defined in: guardrails/types.ts:180

Handler called when a guardrail is triggered
