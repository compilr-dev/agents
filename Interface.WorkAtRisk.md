---
title: "WorkAtRisk"
parent: Interfaces
nav_order: 1
---


# Interface: WorkAtRisk

Defined in: episodes/types.ts:192

Summary of work that would be at risk from a destructive operation.
Used by guardrails and rehearsal to warn agents before they destroy work.

## Properties

### agentAttribution

```ts
agentAttribution: string[];
```

Defined in: episodes/types.ts:200

Agents who did the work (e.g., ['default (abc123)', 'backend (xyz999)'])

### episodes

```ts
episodes: WorkEpisode[];
```

Defined in: episodes/types.ts:194

Episodes involving the affected files

### totalEffort

```ts
totalEffort: Effort;
```

Defined in: episodes/types.ts:197

Maximum effort across at-risk episodes

### warningMessage

```ts
warningMessage: string;
```

Defined in: episodes/types.ts:203

Human-readable warning message
