---
title: "FileAccessTrackerOptions"
parent: Interfaces
nav_order: 1
---


# Interface: FileAccessTrackerOptions

Defined in: context/file-tracker.ts:58

Options for FileAccessTracker constructor

## Properties

### deduplicateReferences?

```ts
optional deduplicateReferences?: boolean;
```

Defined in: context/file-tracker.ts:69

Deduplicate references (don't track same file twice as 'referenced')

#### Default

```ts
true
```

### inlineThreshold?

```ts
optional inlineThreshold?: number;
```

Defined in: context/file-tracker.ts:76

Maximum line count for a file to have its content stored inline.
Files with more lines than this threshold will only store path/lineCount.

#### Default

```ts
200
```

### maxContentEntries?

```ts
optional maxContentEntries?: number;
```

Defined in: context/file-tracker.ts:83

Maximum number of files that can have stored content at once.
When exceeded, oldest content entries are evicted (path still tracked).

#### Default

```ts
10
```

### maxEntries?

```ts
optional maxEntries?: number;
```

Defined in: context/file-tracker.ts:63

Maximum number of entries to track

#### Default

```ts
100
```
