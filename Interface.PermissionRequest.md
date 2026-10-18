---
title: "PermissionRequest"
parent: Interfaces
nav_order: 1
---


# Interface: PermissionRequest

Defined in: permissions/types.ts:46

Permission request passed to the handler

## Properties

### description?

```ts
optional description?: string;
```

Defined in: permissions/types.ts:65

Description of why permission is needed

### input

```ts
input: Record<string, unknown>;
```

Defined in: permissions/types.ts:55

Input arguments for the tool

### level

```ts
level: PermissionLevel;
```

Defined in: permissions/types.ts:60

Permission level that triggered the request

### preview?

```ts
optional preview?: string;
```

Defined in: permissions/types.ts:70

Formatted preview of what the tool will do

### toolName

```ts
toolName: string;
```

Defined in: permissions/types.ts:50

Name of the tool requesting permission
