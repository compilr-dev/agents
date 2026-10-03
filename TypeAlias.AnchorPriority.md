---
title: "AnchorPriority"
parent: Type Aliases
nav_order: 1
---


# Type Alias: AnchorPriority

```ts
type AnchorPriority = "critical" | "safety" | "info";
```

Defined in: anchors/types.ts:17

Priority levels for anchors
- critical: Must remember, highest priority (e.g., "we just implemented X")
- safety: Check before acting (e.g., "verify before git reset")
- info: Useful context (e.g., "modified files this session")
