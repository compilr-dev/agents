---
title: "SkillInvokeOptions"
parent: Interfaces
nav_order: 1
---


# Interface: SkillInvokeOptions

Defined in: skills/index.ts:72

Options for skill invocation

## Properties

### context?

```ts
optional context?: string;
```

Defined in: skills/index.ts:82

Additional context to prepend to the prompt

### variables?

```ts
optional variables?: Record<string, string>;
```

Defined in: skills/index.ts:77

Variables to interpolate into the skill prompt
Use {{variable}} syntax in the prompt template
