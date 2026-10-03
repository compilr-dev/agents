---
title: "Guardrail"
parent: Interfaces
nav_order: 1
---


# Interface: Guardrail

Defined in: guardrails/types.ts:19

A guardrail definition

## Properties

### action

```ts
action: GuardrailAction;
```

Defined in: guardrails/types.ts:43

Action to take when triggered

### description

```ts
description: string;
```

Defined in: guardrails/types.ts:33

Description of what this guardrail protects against

### enabled?

```ts
optional enabled?: boolean;
```

Defined in: guardrails/types.ts:58

Whether this guardrail is enabled (default: true)

### id

```ts
id: string;
```

Defined in: guardrails/types.ts:23

Unique identifier for this guardrail

### message

```ts
message: string;
```

Defined in: guardrails/types.ts:48

Message to display when triggered

### name

```ts
name: string;
```

Defined in: guardrails/types.ts:28

Human-readable name

### patterns

```ts
patterns: RegExp[];
```

Defined in: guardrails/types.ts:38

Patterns to match against tool inputs

### scope?

```ts
optional scope?: string[];
```

Defined in: guardrails/types.ts:53

Which tools this guardrail applies to (empty = all tools)

### tags?

```ts
optional tags?: string[];
```

Defined in: guardrails/types.ts:63

Tags for grouping/filtering guardrails
