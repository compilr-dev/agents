---
title: "DelegationEvent"
parent: Type Aliases
nav_order: 1
---


# Type Alias: DelegationEvent

```ts
type DelegationEvent = 
  | {
  delegationId: string;
  originalTokens: number;
  toolName: string;
  type: "delegation:started";
}
  | {
  delegationId: string;
  originalTokens: number;
  strategy: "llm" | "extractive";
  summaryTokens: number;
  toolName: string;
  type: "delegation:completed";
}
  | {
  error: string;
  toolName: string;
  type: "delegation:failed";
}
  | {
  delegationId: string;
  found: boolean;
  type: "delegation:recall";
};
```

Defined in: context/delegation-types.ts:78

Events emitted during the delegation lifecycle.
