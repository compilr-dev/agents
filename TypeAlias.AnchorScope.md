---
title: "AnchorScope"
parent: Type Aliases
nav_order: 1
---


# Type Alias: AnchorScope

```ts
type AnchorScope = "session" | "persistent" | "temporary";
```

Defined in: anchors/types.ts:25

Scope determines anchor lifetime
- session: Lives for the current session only
- persistent: Saved to disk, survives across sessions
- temporary: Auto-expires after a duration or event
