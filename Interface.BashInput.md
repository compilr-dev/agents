---
title: "BashInput"
parent: Interfaces
nav_order: 1
---


# Interface: BashInput

Defined in: tools/builtin/bash.ts:16

Input parameters for bash tool

## Properties

### command

```ts
command: string;
```

Defined in: tools/builtin/bash.ts:20

Command to execute

### cwd?

```ts
optional cwd?: string;
```

Defined in: tools/builtin/bash.ts:25

Working directory for the command

### description?

```ts
optional description?: string;
```

Defined in: tools/builtin/bash.ts:47

Description of what this command does (for display purposes)

### env?

```ts
optional env?: Record<string, string>;
```

Defined in: tools/builtin/bash.ts:36

Environment variables to set

### run\_in\_background?

```ts
optional run_in_background?: boolean;
```

Defined in: tools/builtin/bash.ts:42

Run command in background and return immediately with a shell ID.
Use bash_output tool to retrieve output later.

### timeout?

```ts
optional timeout?: number;
```

Defined in: tools/builtin/bash.ts:31

Timeout in milliseconds (default: 60000 = 1 minute)
Ignored when run_in_background is true
