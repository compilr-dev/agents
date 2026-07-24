---
title: "ContextCategory"
parent: Type Aliases
nav_order: 1
---


# Type Alias: ContextCategory

```ts
type ContextCategory = "system" | "recentMessages" | "toolResults" | "history";
```

Defined in: context/types.ts:20

Context categories for budget allocation

Each category has its own budget, preventing one type of content
from consuming space meant for another.
