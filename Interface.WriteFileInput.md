---
title: "WriteFileInput"
parent: Interfaces
nav_order: 1
---


# Interface: WriteFileInput

Defined in: tools/builtin/write-file.ts:14

Input parameters for write_file tool

## Properties

### append?

```ts
optional append?: boolean;
```

Defined in: tools/builtin/write-file.ts:38

Append to file instead of overwriting (default: false)

### content

```ts
content: string;
```

Defined in: tools/builtin/write-file.ts:23

Content to write to the file

### createDirs?

```ts
optional createDirs?: boolean;
```

Defined in: tools/builtin/write-file.ts:33

Create parent directories if they don't exist (default: true)

### encoding?

```ts
optional encoding?: BufferEncoding;
```

Defined in: tools/builtin/write-file.ts:28

Encoding to use (default: utf-8)

### path

```ts
path: string;
```

Defined in: tools/builtin/write-file.ts:18

Path to the file to write
