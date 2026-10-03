---
title: "FileAccess"
parent: Interfaces
nav_order: 1
---


# Interface: FileAccess

Defined in: context/file-tracker.ts:32

Record of a file access

## Properties

### content?

```ts
optional content?: string;
```

Defined in: context/file-tracker.ts:49

Stored file content (only for small reads, used for post-compaction restoration)

### lineCount?

```ts
optional lineCount?: number;
```

Defined in: context/file-tracker.ts:43

Number of lines (for 'read' type)

### path

```ts
path: string;
```

Defined in: context/file-tracker.ts:34

Absolute file path

### summary?

```ts
optional summary?: string;
```

Defined in: context/file-tracker.ts:46

Optional summary of what was found/changed

### timestamp

```ts
timestamp: number;
```

Defined in: context/file-tracker.ts:40

When accessed (timestamp)

### tokenCount?

```ts
optional tokenCount?: number;
```

Defined in: context/file-tracker.ts:52

Token count of stored content

### type

```ts
type: FileAccessType;
```

Defined in: context/file-tracker.ts:37

Type of access
