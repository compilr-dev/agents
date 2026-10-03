---
title: "GuardrailResult"
parent: Interfaces
nav_order: 1
---


# Interface: GuardrailResult

Defined in: guardrails/types.ts:84

Result of checking a guardrail

## Properties

### action?

```ts
optional action?: GuardrailAction;
```

Defined in: guardrails/types.ts:103

The action to take

### guardrail?

```ts
optional guardrail?: Guardrail;
```

Defined in: guardrails/types.ts:93

The guardrail that was triggered (if any)

### input?

```ts
optional input?: unknown;
```

Defined in: guardrails/types.ts:113

The input that triggered the guardrail

### match?

```ts
optional match?: string;
```

Defined in: guardrails/types.ts:98

The matched pattern (if any)

### subcommand?

```ts
optional subcommand?: string;
```

Defined in: guardrails/types.ts:118

The specific subcommand that triggered (compound commands only)

### subcommandIndex?

```ts
optional subcommandIndex?: number;
```

Defined in: guardrails/types.ts:123

0-based index of the subcommand in the compound command

### toolName?

```ts
optional toolName?: string;
```

Defined in: guardrails/types.ts:108

The tool that triggered the guardrail

### triggered

```ts
triggered: boolean;
```

Defined in: guardrails/types.ts:88

Whether any guardrail was triggered
