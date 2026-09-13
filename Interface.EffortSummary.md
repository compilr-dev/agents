---
title: "EffortSummary"
parent: Interfaces
nav_order: 1
---


# Interface: EffortSummary

Defined in: episodes/types.ts:136

Summary of effort across multiple episodes.

## Properties

### agents

```ts
agents: string[];
```

Defined in: episodes/types.ts:147

Unique agent IDs involved

### description

```ts
description: string;
```

Defined in: episodes/types.ts:150

Human-readable description

### episodeCount

```ts
episodeCount: number;
```

Defined in: episodes/types.ts:138

Number of episodes included

### timeSpentMs

```ts
timeSpentMs: number;
```

Defined in: episodes/types.ts:144

Total time spent in milliseconds

### totalEffort

```ts
totalEffort: Effort;
```

Defined in: episodes/types.ts:141

Maximum effort level across episodes
