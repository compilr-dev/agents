---
title: "PermissionHandlerResponse"
parent: Type Aliases
nav_order: 1
---


# Type Alias: PermissionHandlerResponse

```ts
type PermissionHandlerResponse = 
  | boolean
  | {
  allowed: boolean;
  reason?: string;
};
```

Defined in: permissions/types.ts:122

Response shape from a permission handler.

Either a plain boolean (legacy — backward compatible) OR a structured
object that can carry an optional reason. The reason is delivered to
the agent inline with the tool's permission-denied error so the agent
sees the user's context immediately, in the same turn.

## Example

```typescript
// Legacy (still supported):
return true;
return false;

// With reason:
return { allowed: false, reason: 'Use project_document_add instead' };
return { allowed: true };
```
