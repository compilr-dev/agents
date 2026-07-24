---
title: "PermissionHandler"
parent: Type Aliases
nav_order: 1
---


# Type Alias: PermissionHandler

```ts
type PermissionHandler = (request) => 
  | PermissionHandlerResponse
| Promise<PermissionHandlerResponse>;
```

Defined in: permissions/types.ts:146

Handler called when permission is needed

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `request` | [`PermissionRequest`](Interface.PermissionRequest.md) | Information about the permission request |

## Returns

  \| [`PermissionHandlerResponse`](TypeAlias.PermissionHandlerResponse.md)
  \| `Promise`\<[`PermissionHandlerResponse`](TypeAlias.PermissionHandlerResponse.md)\>

true to allow / false to deny — or { allowed, reason? } to
         carry context (especially useful when denying with a message)

## Example

```typescript
const handler: PermissionHandler = async (request) => {
  // Show UI prompt to user
  const result = await showConfirmDialog(
    `Allow ${request.toolName}?`,
    request.description
  );
  if (!result.allowed && result.message) {
    return { allowed: false, reason: result.message };
  }
  return result.allowed;
};
```
