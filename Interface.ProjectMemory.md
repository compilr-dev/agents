---
title: "ProjectMemory"
parent: Interfaces
nav_order: 1
---


# Interface: ProjectMemory

Defined in: memory/types.ts:40

Result of loading project memory

## Properties

### content

```ts
content: string;
```

Defined in: memory/types.ts:44

Combined content from all files

### estimatedTokens

```ts
estimatedTokens: number;
```

Defined in: memory/types.ts:48

Total token estimate (tiktoken cl100k_base)

### files

```ts
files: MemoryFile[];
```

Defined in: memory/types.ts:42

All loaded memory files

### rootDir

```ts
rootDir: string;
```

Defined in: memory/types.ts:46

The root directory where search started
