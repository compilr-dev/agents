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
  error?: string;
  fallback: "extractive";
  reason: "error" | "empty" | "aborted";
  toolName: string;
  type: "delegation:llm-failed";
}
  | {
  delegationId: string;
  found: boolean;
  type: "delegation:recall";
};
```

Defined in: context/delegation-types.ts:78

Events emitted during the delegation lifecycle.

## Union Members

### Type Literal

```ts
{
  delegationId: string;
  originalTokens: number;
  toolName: string;
  type: "delegation:started";
}
```

### Type Literal

```ts
{
  delegationId: string;
  originalTokens: number;
  strategy: "llm" | "extractive";
  summaryTokens: number;
  toolName: string;
  type: "delegation:completed";
}
```

### Type Literal

```ts
{
  error: string;
  toolName: string;
  type: "delegation:failed";
}
```

### Type Literal

```ts
{
  delegationId: string;
  error?: string;
  fallback: "extractive";
  reason: "error" | "empty" | "aborted";
  toolName: string;
  type: "delegation:llm-failed";
}
```

The LLM summarizer failed and the extractive summarizer was used instead.

⚠️ NOT `delegation:failed`: delegation SUCCEEDED, with a worse summary. This exists because
`summarizeLLM` swallowed every error and returned null, so the fallback was indistinguishable
from the configured behaviour — including, measurably, a 400 on every call for a model that
refuses `temperature` (the summariser always sends `temperature: 0`). `strategy: 'llm'` was
silently never honoured on those models.

| Name | Type | Description | Defined in |
| ------ | ------ | ------ | ------ |
| `delegationId` | `string` | - | context/delegation-types.ts:110 |
| `error?` | `string` | Provider error text; absent for 'empty' and 'aborted'. | context/delegation-types.ts:114 |
| `fallback` | `"extractive"` | What produced the summary instead. | context/delegation-types.ts:116 |
| `reason` | `"error"` \| `"empty"` \| `"aborted"` | Why the LLM summary was not used. | context/delegation-types.ts:112 |
| `toolName` | `string` | - | context/delegation-types.ts:109 |
| `type` | `"delegation:llm-failed"` | - | context/delegation-types.ts:108 |

### Type Literal

```ts
{
  delegationId: string;
  found: boolean;
  type: "delegation:recall";
}
```
