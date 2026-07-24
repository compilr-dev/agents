---
title: "AffectedFile"
parent: Interfaces
nav_order: 1
---


# Interface: AffectedFile

Defined in: rehearsal/types.ts:29

Information about a file that would be affected

## Properties

### changeType

```ts
changeType: "reset" | "delete" | "overwrite" | "modify";
```

Defined in: rehearsal/types.ts:38

Type of change that would occur

### hasUncommittedChanges?

```ts
optional hasUncommittedChanges?: boolean;
```

Defined in: rehearsal/types.ts:58

Whether this file has uncommitted changes (for git operations)

### lastModified?

```ts
optional lastModified?: Date;
```

Defined in: rehearsal/types.ts:48

When the file was last modified

### linesAffected?

```ts
optional linesAffected?: number;
```

Defined in: rehearsal/types.ts:43

Number of lines that would be affected (if applicable)

### path

```ts
path: string;
```

Defined in: rehearsal/types.ts:33

Path to the file

### size?

```ts
optional size?: number;
```

Defined in: rehearsal/types.ts:53

Size of the file in bytes
