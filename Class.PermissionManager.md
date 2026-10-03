---
title: "PermissionManager"
parent: Classes
nav_order: 1
---


# Class: PermissionManager

Defined in: permissions/manager.ts:130

PermissionManager handles tool-level permission checks

## Constructors

### Constructor

```ts
new PermissionManager(options?): PermissionManager;
```

Defined in: permissions/manager.ts:144

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `options` | [`PermissionManagerOptions`](Interface.PermissionManagerOptions.md) |

#### Returns

`PermissionManager`

## Accessors

### isEnabled

#### Get Signature

```ts
get isEnabled(): boolean;
```

Defined in: permissions/manager.ts:447

Check if permissions are enabled

##### Returns

`boolean`

### size

#### Get Signature

```ts
get size(): number;
```

Defined in: permissions/manager.ts:440

Get the number of rules

##### Returns

`number`

## Methods

### addRule()

```ts
addRule(rule): this;
```

Defined in: permissions/manager.ts:168

Add a permission rule

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `rule` | [`ToolPermission`](Interface.ToolPermission.md) |

#### Returns

`this`

### check()

```ts
check(toolName, input): Promise<PermissionCheckResult>;
```

Defined in: permissions/manager.ts:231

Check if a tool has permission to execute

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `toolName` | `string` | Name of the tool |
| `input` | `Record`\<`string`, `unknown`\> | Tool input arguments |

#### Returns

`Promise`\<[`PermissionCheckResult`](Interface.PermissionCheckResult.md)\>

Permission check result

### checkAndProceed()

```ts
checkAndProceed(toolName, input): Promise<{
  proceed: boolean;
  result: PermissionCheckResult;
}>;
```

Defined in: permissions/manager.ts:311

Check and handle permission, returning whether to proceed

Convenience method that combines check() with handling

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `toolName` | `string` |
| `input` | `Record`\<`string`, `unknown`\> |

#### Returns

`Promise`\<\{
  `proceed`: `boolean`;
  `result`: [`PermissionCheckResult`](Interface.PermissionCheckResult.md);
\}\>

### clearSessionGrants()

```ts
clearSessionGrants(): void;
```

Defined in: permissions/manager.ts:374

Clear all session-level permissions

#### Returns

`void`

### getAllRules()

```ts
getAllRules(): ToolPermission[];
```

Defined in: permissions/manager.ts:218

Get all permission rules

#### Returns

[`ToolPermission`](Interface.ToolPermission.md)[]

### getLevel()

```ts
getLevel(toolName): PermissionLevel;
```

Defined in: permissions/manager.ts:411

Get the effective permission level for a tool

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `toolName` | `string` |

#### Returns

[`PermissionLevel`](TypeAlias.PermissionLevel.md)

### getRule()

```ts
getRule(toolName): ToolPermission | undefined;
```

Defined in: permissions/manager.ts:200

Get a permission rule by tool name

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `toolName` | `string` |

#### Returns

[`ToolPermission`](Interface.ToolPermission.md) \| `undefined`

### getSessionGrants()

```ts
getSessionGrants(): string[];
```

Defined in: permissions/manager.ts:381

Get all tools with session-level permission

#### Returns

`string`[]

### grantSession()

```ts
grantSession(toolName): void;
```

Defined in: permissions/manager.ts:360

Grant session-level permission for a tool

This allows the tool to execute for the remainder of the session
without asking again.

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `toolName` | `string` |

#### Returns

`void`

### hasSessionGrant()

```ts
hasSessionGrant(toolName): boolean;
```

Defined in: permissions/manager.ts:388

Check if a tool has session-level permission

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `toolName` | `string` |

#### Returns

`boolean`

### onEvent()

```ts
onEvent(handler): () => void;
```

Defined in: permissions/manager.ts:419

Register an event handler

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `handler` | [`PermissionEventHandler`](TypeAlias.PermissionEventHandler.md) |

#### Returns

() => `void`

### removeRule()

```ts
removeRule(toolName): boolean;
```

Defined in: permissions/manager.ts:185

Remove a permission rule by tool name

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `toolName` | `string` |

#### Returns

`boolean`

### revokeSession()

```ts
revokeSession(toolName): boolean;
```

Defined in: permissions/manager.ts:367

Revoke session-level permission for a tool

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `toolName` | `string` |

#### Returns

`boolean`

### setLevel()

```ts
setLevel(
   toolName, 
   level, 
   description?): this;
```

Defined in: permissions/manager.ts:397

Set the permission level for a tool

Convenience method for adding/updating a rule

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `toolName` | `string` |
| `level` | [`PermissionLevel`](TypeAlias.PermissionLevel.md) |
| `description?` | `string` |

#### Returns

`this`
