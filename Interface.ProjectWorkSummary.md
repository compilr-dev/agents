---
title: "ProjectWorkSummary"
parent: Interfaces
nav_order: 1
---


# Interface: ProjectWorkSummary

Defined in: episodes/types.ts:156

Project-level work summary with breakdown.

## Properties

### agentBreakdown

```ts
agentBreakdown: {
  agentId: string;
  episodeCount: number;
  maxEffort: Effort;
  timeSpentMs: number;
}[];
```

Defined in: episodes/types.ts:167

Effort breakdown by agent

#### agentId

```ts
agentId: string;
```

#### episodeCount

```ts
episodeCount: number;
```

#### maxEffort

```ts
maxEffort: Effort;
```

#### timeSpentMs

```ts
timeSpentMs: number;
```

### episodeCount

```ts
episodeCount: number;
```

Defined in: episodes/types.ts:158

Total number of episodes

### timeSpentMs

```ts
timeSpentMs: number;
```

Defined in: episodes/types.ts:164

Total time spent in milliseconds

### topFiles

```ts
topFiles: {
  path: string;
  touchCount: number;
}[];
```

Defined in: episodes/types.ts:175

Most frequently touched files

#### path

```ts
path: string;
```

#### touchCount

```ts
touchCount: number;
```

### totalEffort

```ts
totalEffort: Effort;
```

Defined in: episodes/types.ts:161

Maximum effort level

### uncommittedWork

```ts
uncommittedWork: WorkEpisode[];
```

Defined in: episodes/types.ts:181

Episodes since the last git commit
