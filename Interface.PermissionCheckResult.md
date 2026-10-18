---
title: "PermissionCheckResult"
parent: Interfaces
nav_order: 1
---


# Interface: PermissionCheckResult

Defined in: permissions/types.ts:76

Result of a permission check

## Properties

### allowed

```ts
allowed: boolean;
```

Defined in: permissions/types.ts:80

Whether execution is allowed

### askedUser

```ts
askedUser: boolean;
```

Defined in: permissions/types.ts:90

Whether user confirmation was required

### level

```ts
level: PermissionLevel;
```

Defined in: permissions/types.ts:85

The permission level that applied

### reason?

```ts
optional reason?: string;
```

Defined in: permissions/types.ts:100

Reason for denial (if not allowed)

### rule?

```ts
optional rule?: ToolPermission;
```

Defined in: permissions/types.ts:95

The tool permission rule that matched (if any)
