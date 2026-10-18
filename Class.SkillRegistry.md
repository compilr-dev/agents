---
title: "SkillRegistry"
parent: Classes
nav_order: 1
---


# Class: SkillRegistry

Defined in: skills/index.ts:88

Skill Registry - Manages skill registration and invocation

## Constructors

### Constructor

```ts
new SkillRegistry(): SkillRegistry;
```

#### Returns

`SkillRegistry`

## Accessors

### size

#### Get Signature

```ts
get size(): number;
```

Defined in: skills/index.ts:240

Get skill count

##### Returns

`number`

## Methods

### clear()

```ts
clear(): void;
```

Defined in: skills/index.ts:168

Clear all skills

#### Returns

`void`

### disable()

```ts
disable(name): boolean;
```

Defined in: skills/index.ts:185

Disable a skill

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `name` | `string` |

#### Returns

`boolean`

### enable()

```ts
enable(name): boolean;
```

Defined in: skills/index.ts:175

Enable a skill

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `name` | `string` |

#### Returns

`boolean`

### get()

```ts
get(name): Skill | undefined;
```

Defined in: skills/index.ts:119

Get a skill by name

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `name` | `string` |

#### Returns

[`Skill`](Interface.Skill.md) \| `undefined`

### getAll()

```ts
getAll(): Skill[];
```

Defined in: skills/index.ts:133

Get all registered skills

#### Returns

[`Skill`](Interface.Skill.md)[]

### getByTag()

```ts
getByTag(tag): Skill[];
```

Defined in: skills/index.ts:147

Get skills by tag

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `tag` | `string` |

#### Returns

[`Skill`](Interface.Skill.md)[]

### getEnabled()

```ts
getEnabled(): Skill[];
```

Defined in: skills/index.ts:140

Get all enabled skills

#### Returns

[`Skill`](Interface.Skill.md)[]

### getNames()

```ts
getNames(): string[];
```

Defined in: skills/index.ts:154

Get skill names

#### Returns

`string`[]

### has()

```ts
has(name): boolean;
```

Defined in: skills/index.ts:126

Check if a skill exists

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `name` | `string` |

#### Returns

`boolean`

### invoke()

```ts
invoke(name, options?): SkillInvocationResult;
```

Defined in: skills/index.ts:195

Invoke a skill by name

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `name` | `string` |
| `options?` | [`SkillInvokeOptions`](Interface.SkillInvokeOptions.md) |

#### Returns

[`SkillInvocationResult`](Interface.SkillInvocationResult.md)

### register()

```ts
register(skill): void;
```

Defined in: skills/index.ts:94

Register a new skill

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `skill` | [`Skill`](Interface.Skill.md) |

#### Returns

`void`

### registerAll()

```ts
registerAll(skills): void;
```

Defined in: skills/index.ts:110

Register multiple skills at once

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `skills` | [`Skill`](Interface.Skill.md)[] |

#### Returns

`void`

### remove()

```ts
remove(name): boolean;
```

Defined in: skills/index.ts:161

Remove a skill

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `name` | `string` |

#### Returns

`boolean`
