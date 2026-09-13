---
title: "GuardrailInput"
parent: Interfaces
nav_order: 1
---


# Interface: GuardrailInput

Defined in: guardrails/types.ts:69

Input for adding a custom guardrail

## Properties

### action

```ts
action: GuardrailAction;
```

Defined in: guardrails/types.ts:74

### description

```ts
description: string;
```

Defined in: guardrails/types.ts:72

### enabled?

```ts
optional enabled?: boolean;
```

Defined in: guardrails/types.ts:77

### id

```ts
id: string;
```

Defined in: guardrails/types.ts:70

### message

```ts
message: string;
```

Defined in: guardrails/types.ts:75

### name

```ts
name: string;
```

Defined in: guardrails/types.ts:71

### patterns

```ts
patterns: RegExp[];
```

Defined in: guardrails/types.ts:73

### scope?

```ts
optional scope?: string[];
```

Defined in: guardrails/types.ts:76

### tags?

```ts
optional tags?: string[];
```

Defined in: guardrails/types.ts:78
