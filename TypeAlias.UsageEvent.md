---
title: "UsageEvent"
parent: Type Aliases
nav_order: 1
---


# Type Alias: UsageEvent

```ts
type UsageEvent = 
  | {
  record: UsageRecord;
  stats: UsageStats;
  type: "usage:recorded";
}
  | {
  status: BudgetStatus;
  threshold: number;
  type: "usage:budget_warning";
}
  | {
  status: BudgetStatus;
  type: "usage:budget_exceeded";
}
  | {
  previousStats: UsageStats;
  type: "usage:reset";
};
```

Defined in: costs/types.ts:127

Usage tracker events
