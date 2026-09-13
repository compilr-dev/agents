---
title: "MemoryFile"
parent: Interfaces
nav_order: 1
---


# Interface: MemoryFile

Defined in: memory/types.ts:22

A loaded memory file with its content and metadata

## Properties

### content

```ts
content: string;
```

Defined in: memory/types.ts:26

File content

### matchedPattern

```ts
matchedPattern: string;
```

Defined in: memory/types.ts:30

The pattern that matched this file

### modifiedAt

```ts
modifiedAt: Date;
```

Defined in: memory/types.ts:34

Last modified timestamp

### path

```ts
path: string;
```

Defined in: memory/types.ts:24

Absolute path to the file

### relativePath

```ts
relativePath: string;
```

Defined in: memory/types.ts:28

Relative path from the search root

### size

```ts
size: number;
```

Defined in: memory/types.ts:32

File size in bytes
