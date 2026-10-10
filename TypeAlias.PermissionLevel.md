---
title: "PermissionLevel"
parent: Type Aliases
nav_order: 1
---


# Type Alias: PermissionLevel

```ts
type PermissionLevel = "always" | "session" | "once" | "deny";
```

Defined in: permissions/types.ts:16

Permission levels for tool execution

- 'always': Tool can execute without asking (trusted tools)
- 'session': Ask once per session, then allow for remainder
- 'once': Ask every time the tool is invoked
- 'deny': Never allow execution (blocked tools)
