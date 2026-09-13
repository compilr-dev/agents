---
title: "FileAccessTracker"
parent: Classes
nav_order: 1
---


# Class: FileAccessTracker

Defined in: context/file-tracker.ts:157

Tracks file accesses during agent sessions for context restoration hints.

## Example

```typescript
const tracker = new FileAccessTracker();

// Track file accesses
tracker.trackRead('/path/to/file.ts', 597);
tracker.trackReference('/path/to/other.ts');
tracker.trackModification('/path/to/file.ts', 'Added function');

// Get restoration hints after compaction
const hints = tracker.formatRestorationHints();
console.log(hints);
```

## Constructors

### Constructor

```ts
new FileAccessTracker(options?): FileAccessTracker;
```

Defined in: context/file-tracker.ts:164

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `options` | [`FileAccessTrackerOptions`](Interface.FileAccessTrackerOptions.md) |

#### Returns

`FileAccessTracker`

## Accessors

### size

#### Get Signature

```ts
get size(): number;
```

Defined in: context/file-tracker.ts:447

Get the number of tracked files

##### Returns

`number`

## Methods

### clear()

```ts
clear(): void;
```

Defined in: context/file-tracker.ts:440

Clear all tracked accesses

#### Returns

`void`

### formatRestorationHints()

```ts
formatRestorationHints(options?): string;
```

Defined in: context/file-tracker.ts:317

Format restoration hints for injection after compaction

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `options` | [`FormatHintsOptions`](Interface.FormatHintsOptions.md) |

#### Returns

`string`

### formatRestorationHintsWithContent()

```ts
formatRestorationHintsWithContent(options?): RestorationHintMessage[];
```

Defined in: context/file-tracker.ts:375

Format restoration hints with inline file content (Claude Code style).

Small files with stored content are inlined up to a token budget.
Large files or files exceeding the budget get reference-only hints.
Each file produces a separate hint message for individual injection.

Priority order for inlining:
1. Modified files (most critical context)
2. Read files, most recent first
3. Once budget exhausted → remaining become reference-only
4. Referenced-only files → always reference-only

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `options?` | \{ `maxInlineTokens?`: `number`; \} | - |
| `options.maxInlineTokens?` | `number` | Total token budget for all inline content (default: 4000) |

#### Returns

[`RestorationHintMessage`](Interface.RestorationHintMessage.md)[]

### getAccess()

```ts
getAccess(filePath): FileAccess | undefined;
```

Defined in: context/file-tracker.ts:292

Get access record for a specific file

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `filePath` | `string` |

#### Returns

[`FileAccess`](Interface.FileAccess.md) \| `undefined`

### getAccesses()

```ts
getAccesses(options?): FileAccess[];
```

Defined in: context/file-tracker.ts:259

Get all file accesses, optionally filtered

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `options?` | \{ `since?`: `number`; `type?`: [`FileAccessType`](TypeAlias.FileAccessType.md); \} |
| `options.since?` | `number` |
| `options.type?` | [`FileAccessType`](TypeAlias.FileAccessType.md) |

#### Returns

[`FileAccess`](Interface.FileAccess.md)[]

### getRecentAccesses()

```ts
getRecentAccesses(limit?): FileAccess[];
```

Defined in: context/file-tracker.ts:278

Get most recent file accesses

#### Parameters

| Parameter | Type | Default value |
| ------ | ------ | ------ |
| `limit` | `number` | `10` |

#### Returns

[`FileAccess`](Interface.FileAccess.md)[]

### getStats()

```ts
getStats(): FileAccessStats;
```

Defined in: context/file-tracker.ts:299

Get statistics about file accesses

#### Returns

[`FileAccessStats`](Interface.FileAccessStats.md)

### hasAccessed()

```ts
hasAccessed(filePath): boolean;
```

Defined in: context/file-tracker.ts:285

Check if a file has been accessed

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `filePath` | `string` |

#### Returns

`boolean`

### trackModification()

```ts
trackModification(filePath, summary?): void;
```

Defined in: context/file-tracker.ts:239

Track a file that was modified (written or edited)

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `filePath` | `string` |
| `summary?` | `string` |

#### Returns

`void`

### trackRead()

```ts
trackRead(
   filePath, 
   lineCount, 
   summary?, 
   content?): void;
```

Defined in: context/file-tracker.ts:178

Track a file that was fully read

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `filePath` | `string` |
| `lineCount` | `number` |
| `summary?` | `string` |
| `content?` | `string` |

#### Returns

`void`

### trackReference()

```ts
trackReference(filePath): void;
```

Defined in: context/file-tracker.ts:211

Track a file that was referenced (e.g., appeared in grep/glob results)

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `filePath` | `string` |

#### Returns

`void`
