---
title: "GuardrailContext"
parent: Interfaces
nav_order: 1
---


# Interface: GuardrailContext

Defined in: guardrails/types.ts:129

Context passed to guardrail handlers

## Properties

### input

```ts
input: unknown;
```

Defined in: guardrails/types.ts:138

The tool input

### inputString

```ts
inputString: string;
```

Defined in: guardrails/types.ts:143

The stringified input used for pattern matching

### toolName

```ts
toolName: string;
```

Defined in: guardrails/types.ts:133

The tool being called
