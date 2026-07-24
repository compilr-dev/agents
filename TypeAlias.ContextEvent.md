---
title: "ContextEvent"
parent: Type Aliases
nav_order: 1
---


# Type Alias: ContextEvent

```ts
type ContextEvent = 
  | {
  threshold: number;
  type: "context_warning";
  utilization: number;
}
  | {
  result: CompactionResult;
  type: "context_compacted";
}
  | {
  result: SummarizationResult;
  type: "context_summarized";
}
  | {
  result: FilteringResult;
  type: "content_filtered";
};
```

Defined in: context/types.ts:405

Context-related events
