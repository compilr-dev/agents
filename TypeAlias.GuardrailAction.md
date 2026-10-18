---
title: "GuardrailAction"
parent: Type Aliases
nav_order: 1
---


# Type Alias: GuardrailAction

```ts
type GuardrailAction = "warn" | "confirm" | "block";
```

Defined in: guardrails/types.ts:14

Action to take when a guardrail is triggered
- warn: Log warning but proceed with execution
- confirm: Require confirmation before proceeding
- block: Prevent execution entirely
