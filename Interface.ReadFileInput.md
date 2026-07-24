---
title: "ReadFileInput"
parent: Interfaces
nav_order: 1
---


# Interface: ReadFileInput

Defined in: tools/builtin/read-file.ts:24

Input parameters for read_file tool

## Properties

### encoding?

```ts
optional encoding?: BufferEncoding;
```

Defined in: tools/builtin/read-file.ts:33

Encoding to use (default: utf-8)

### maxLines?

```ts
optional maxLines?: number;
```

Defined in: tools/builtin/read-file.ts:38

Maximum number of lines to read (default: all)

### path

```ts
path: string;
```

Defined in: tools/builtin/read-file.ts:28

Path to the file to read

### startLine?

```ts
optional startLine?: number;
```

Defined in: tools/builtin/read-file.ts:43

Line offset to start reading from (1-indexed, default: 1)
