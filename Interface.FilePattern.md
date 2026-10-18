---
title: "FilePattern"
parent: Interfaces
nav_order: 1
---


# Interface: FilePattern

Defined in: memory/types.ts:54

File pattern configuration for discovery

## Properties

### description?

```ts
optional description?: string;
```

Defined in: memory/types.ts:60

Description of what this pattern matches

### pattern

```ts
pattern: string;
```

Defined in: memory/types.ts:56

Glob pattern or exact filename

### priority

```ts
priority: number;
```

Defined in: memory/types.ts:58

Priority (lower = higher priority, loaded first)
