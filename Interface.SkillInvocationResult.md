---
title: "SkillInvocationResult"
parent: Interfaces
nav_order: 1
---


# Interface: SkillInvocationResult

Defined in: skills/index.ts:47

Result of invoking a skill

## Properties

### error?

```ts
optional error?: string;
```

Defined in: skills/index.ts:66

Error message if invocation failed

### prompt

```ts
prompt: string;
```

Defined in: skills/index.ts:56

The expanded prompt content

### skill

```ts
skill: Skill;
```

Defined in: skills/index.ts:51

The skill that was invoked

### success

```ts
success: boolean;
```

Defined in: skills/index.ts:61

Whether the invocation was successful
