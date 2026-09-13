---
title: "defineSkill"
parent: Functions
nav_order: 1
---


# Function: defineSkill()

```ts
function defineSkill(options): Skill;
```

Defined in: skills/index.ts:248

Helper function to define a skill

## Parameters

| Parameter | Type |
| ------ | ------ |
| `options` | \{ `description`: `string`; `enabled?`: `boolean`; `name`: `string`; `prompt`: `string`; `tags?`: `string`[]; `version?`: `string`; \} |
| `options.description` | `string` |
| `options.enabled?` | `boolean` |
| `options.name` | `string` |
| `options.prompt` | `string` |
| `options.tags?` | `string`[] |
| `options.version?` | `string` |

## Returns

[`Skill`](Interface.Skill.md)
