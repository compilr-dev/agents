---
title: "WorkEpisode"
parent: Interfaces
nav_order: 1
---


# Interface: WorkEpisode

Defined in: episodes/types.ts:27

A single unit of tracked work.
Represents something an agent did — e.g., editing files, running tests, committing.

## Properties

### action

```ts
action: string;
```

Defined in: episodes/types.ts:38

High-level action label (e.g., 'edit', 'test', 'commit', 'refactor')

### agentId

```ts
agentId: string;
```

Defined in: episodes/types.ts:32

Agent ID that performed this work (e.g., 'default', 'backend', 'tester')

### durationMs?

```ts
optional durationMs?: number;
```

Defined in: episodes/types.ts:59

Duration in milliseconds, if tracked

### effort

```ts
effort: Effort;
```

Defined in: episodes/types.ts:56

Estimated effort level

### files

```ts
files: string[];
```

Defined in: episodes/types.ts:44

Files affected by this episode

### id

```ts
id: string;
```

Defined in: episodes/types.ts:29

Unique episode ID (UUID)

### linesChanged?

```ts
optional linesChanged?: number;
```

Defined in: episodes/types.ts:47

Total lines changed (added + removed), if known

### parentEpisode?

```ts
optional parentEpisode?: string;
```

Defined in: episodes/types.ts:71

Parent episode ID (for sub-tasks)

### relatedCommits?

```ts
optional relatedCommits?: string[];
```

Defined in: episodes/types.ts:68

Related git commit hashes

### sessionId

```ts
sessionId: string;
```

Defined in: episodes/types.ts:53

Session ID for grouping episodes within a session

### summary

```ts
summary: string;
```

Defined in: episodes/types.ts:41

Human-readable summary of what was done

### terminalPrefix

```ts
terminalPrefix: string;
```

Defined in: episodes/types.ts:35

Terminal session prefix (first 8 chars of session ID)

### timestamp

```ts
timestamp: string;
```

Defined in: episodes/types.ts:50

ISO timestamp when the episode was recorded

### toolCalls?

```ts
optional toolCalls?: number;
```

Defined in: episodes/types.ts:62

Number of tool calls in this episode

### workItemId?

```ts
optional workItemId?: string;
```

Defined in: episodes/types.ts:65

Related work item ID (from workitem system)
