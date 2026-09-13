---
title: "Skill"
parent: Interfaces
nav_order: 1
---


# Interface: Skill

Defined in: skills/index.ts:12

Skill definition

## Properties

### description

```ts
description: string;
```

Defined in: skills/index.ts:21

Human-readable description of what the skill does

### enabled?

```ts
optional enabled?: boolean;
```

Defined in: skills/index.ts:41

Whether this skill is enabled (default: true)

### name

```ts
name: string;
```

Defined in: skills/index.ts:16

Unique identifier for the skill

### prompt

```ts
prompt: string;
```

Defined in: skills/index.ts:26

The prompt content that will be expanded when the skill is invoked

### tags?

```ts
optional tags?: string[];
```

Defined in: skills/index.ts:31

Optional tags for categorization

### version?

```ts
optional version?: string;
```

Defined in: skills/index.ts:36

Optional version string
