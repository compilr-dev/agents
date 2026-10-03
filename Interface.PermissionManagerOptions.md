---
title: "PermissionManagerOptions"
parent: Interfaces
nav_order: 1
---


# Interface: PermissionManagerOptions

Defined in: permissions/types.ts:165

Configuration for the PermissionManager

## Properties

### defaultLevel?

```ts
optional defaultLevel?: PermissionLevel;
```

Defined in: permissions/types.ts:175

Default permission level for tools not explicitly configured

#### Default

```ts
'always'
```

### enabled?

```ts
optional enabled?: boolean;
```

Defined in: permissions/types.ts:169

Enable permission checking (default: true)

### includeDefaults?

```ts
optional includeDefaults?: boolean;
```

Defined in: permissions/types.ts:196

Whether to include default permission rules for dangerous tools

#### Default

```ts
false
```

### onPermissionRequest?

```ts
optional onPermissionRequest?: PermissionHandler;
```

Defined in: permissions/types.ts:180

Handler called when permission is needed (for 'session' and 'once' levels)

### previewGenerator?

```ts
optional previewGenerator?: PreviewGenerator;
```

Defined in: permissions/types.ts:190

Custom preview generator for permission requests

### rules?

```ts
optional rules?: ToolPermission[];
```

Defined in: permissions/types.ts:185

Tool-specific permission rules
