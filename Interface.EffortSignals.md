---
title: "EffortSignals"
parent: Interfaces
nav_order: 1
---


# Interface: EffortSignals

Defined in: episodes/types.ts:82

Raw signals used to estimate effort.
These are collected from tool calls and timing data.

## Properties

### complexityIndicators

```ts
complexityIndicators: {
  configChanges?: boolean;
  multiLanguage?: boolean;
  newFiles?: boolean;
  tests?: boolean;
};
```

Defined in: episodes/types.ts:99

Complexity indicators detected

#### configChanges?

```ts
optional configChanges?: boolean;
```

Config files were modified

#### multiLanguage?

```ts
optional multiLanguage?: boolean;
```

Multiple languages involved

#### newFiles?

```ts
optional newFiles?: boolean;
```

New files were created (not just edited)

#### tests?

```ts
optional tests?: boolean;
```

Test files were created or modified

### durationMs

```ts
durationMs: number;
```

Defined in: episodes/types.ts:93

Duration in milliseconds

### fileCount

```ts
fileCount: number;
```

Defined in: episodes/types.ts:84

Number of unique files touched

### iterationCount

```ts
iterationCount: number;
```

Defined in: episodes/types.ts:96

Number of edit/write iterations on same files

### linesChanged

```ts
linesChanged: number;
```

Defined in: episodes/types.ts:87

Total lines changed (added + removed)

### toolCallCount

```ts
toolCallCount: number;
```

Defined in: episodes/types.ts:90

Total number of tool calls
