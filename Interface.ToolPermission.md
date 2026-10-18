---
title: "ToolPermission"
parent: Interfaces
nav_order: 1
---


# Interface: ToolPermission

Defined in: permissions/types.ts:21

Permission rule for a specific tool

## Properties

### description?

```ts
optional description?: string;
```

Defined in: permissions/types.ts:35

Human-readable description of why permission is needed

### level

```ts
level: PermissionLevel;
```

Defined in: permissions/types.ts:30

Permission level for this tool

### tags?

```ts
optional tags?: string[];
```

Defined in: permissions/types.ts:40

Tags for grouping permissions

### toolName

```ts
toolName: string;
```

Defined in: permissions/types.ts:25

Tool name or pattern (supports wildcards like 'bash*', '*_file')
