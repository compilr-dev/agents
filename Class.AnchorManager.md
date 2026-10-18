---
title: "AnchorManager"
parent: Classes
nav_order: 1
---


# Class: AnchorManager

Defined in: anchors/manager.ts:58

AnchorManager - Manages critical information that survives context compaction

## Example

```typescript
const manager = new AnchorManager({
  maxAnchors: 20,
  maxTokens: 2000,
  persistPath: '~/.myapp/anchors.json',
});

// Add a session anchor
manager.add({
  content: 'This session we implemented: edit tool, grep tool',
  priority: 'critical',
  scope: 'session',
});

// Get formatted anchors for injection into LLM messages
const formatted = manager.format();
```

## Constructors

### Constructor

```ts
new AnchorManager(options?): AnchorManager;
```

Defined in: anchors/manager.ts:68

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `options` | [`AnchorManagerOptions`](Interface.AnchorManagerOptions.md) |

#### Returns

`AnchorManager`

## Accessors

### size

#### Get Signature

```ts
get size(): number;
```

Defined in: anchors/manager.ts:382

Get the current number of anchors

##### Returns

`number`

## Methods

### add()

```ts
add(input): Anchor;
```

Defined in: anchors/manager.ts:118

Add a new anchor

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `input` | [`AnchorInput`](Interface.AnchorInput.md) | Anchor input (id and createdAt auto-generated if not provided) |

#### Returns

[`Anchor`](Interface.Anchor.md)

The created anchor

### clear()

```ts
clear(options?): number;
```

Defined in: anchors/manager.ts:249

Clear anchors based on criteria

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `options?` | [`AnchorClearOptions`](Interface.AnchorClearOptions.md) |

#### Returns

`number`

### clearByProject()

```ts
clearByProject(projectId): number;
```

Defined in: anchors/manager.ts:330

Clear all anchors for a specific project

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `projectId` | `string` | The project ID |

#### Returns

`number`

Number of anchors removed

### format()

```ts
format(): string;
```

Defined in: anchors/manager.ts:411

Format anchors for injection into LLM messages

Groups anchors by priority and formats them for the system message.

#### Returns

`string`

### get()

```ts
get(id): Anchor | undefined;
```

Defined in: anchors/manager.ts:164

Get an anchor by ID

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |

#### Returns

[`Anchor`](Interface.Anchor.md) \| `undefined`

### getAll()

```ts
getAll(options?): Anchor[];
```

Defined in: anchors/manager.ts:176

Get all anchors, optionally filtered

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `options?` | [`AnchorQueryOptions`](Interface.AnchorQueryOptions.md) |

#### Returns

[`Anchor`](Interface.Anchor.md)[]

### getByProject()

```ts
getByProject(projectId, options?): Anchor[];
```

Defined in: anchors/manager.ts:308

Get all anchors for a specific project

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `projectId` | `string` | The project ID to filter by |
| `options?` | `Omit`\<[`AnchorQueryOptions`](Interface.AnchorQueryOptions.md), `"projectId"` \| `"globalOnly"`\> | Additional query options (priority, scope, tags) |

#### Returns

[`Anchor`](Interface.Anchor.md)[]

### getGlobal()

```ts
getGlobal(options?): Anchor[];
```

Defined in: anchors/manager.ts:320

Get all global anchors (those without a projectId)

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `options?` | `Omit`\<[`AnchorQueryOptions`](Interface.AnchorQueryOptions.md), `"projectId"` \| `"globalOnly"`\> | Additional query options (priority, scope, tags) |

#### Returns

[`Anchor`](Interface.Anchor.md)[]

### getProjectIds()

```ts
getProjectIds(): string[];
```

Defined in: anchors/manager.ts:337

Get list of unique project IDs that have anchors

#### Returns

`string`[]

### getProjectStats()

```ts
getProjectStats(): Map<string | null, number>;
```

Defined in: anchors/manager.ts:364

Get anchor counts grouped by project

#### Returns

`Map`\<`string` \| `null`, `number`\>

Map where keys are project IDs (null for global) and values are counts

### getTotalTokens()

```ts
getTotalTokens(): number;
```

Defined in: anchors/manager.ts:389

Get total tokens used by all anchors

#### Returns

`number`

### getUtilization()

```ts
getUtilization(): number;
```

Defined in: anchors/manager.ts:402

Get token budget utilization (0-1)

#### Returns

`number`

### has()

```ts
has(id): boolean;
```

Defined in: anchors/manager.ts:222

Check if an anchor exists

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |

#### Returns

`boolean`

### hasProjectAnchors()

```ts
hasProjectAnchors(projectId): boolean;
```

Defined in: anchors/manager.ts:350

Check if a project has any anchors

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `projectId` | `string` |

#### Returns

`boolean`

### onEvent()

```ts
onEvent(handler): void;
```

Defined in: anchors/manager.ts:91

Set the event handler for anchor events

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `handler` | [`AnchorEventHandler`](TypeAlias.AnchorEventHandler.md) |

#### Returns

`void`

### remove()

```ts
remove(id): boolean;
```

Defined in: anchors/manager.ts:231

Remove an anchor by ID

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |

#### Returns

`boolean`

true if anchor was removed, false if not found
