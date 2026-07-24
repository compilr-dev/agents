---
title: "ObservationMaskConfig"
parent: Interfaces
nav_order: 1
---


# Interface: ObservationMaskConfig

Defined in: context/observation-masker.ts:27

## Properties

### alwaysMaskEarly

```ts
alwaysMaskEarly: string[];
```

Defined in: context/observation-masker.ts:35

Tool names to mask after just 1 turn (large reads, bash output)

### inputCompaction

```ts
inputCompaction: 
  | false
| Map<string, InputCompactionRule>;
```

Defined in: context/observation-masker.ts:42

Tool input compaction rules (Phase 1b). Keys are tool names.
After the turn threshold, large input fields are removed, keeping only the fields listed.
Set to false to disable input compaction entirely.
Default: compact edit (keep filePath) and write_file (keep path, mode).

### maskAfterTurns

```ts
maskAfterTurns: number;
```

Defined in: context/observation-masker.ts:29

Turns after which tool results are masked (default: 6)

### minCharsToMask

```ts
minCharsToMask: number;
```

Defined in: context/observation-masker.ts:31

Minimum content length (chars) to mask — skip tiny results (default: 400 ≈ 100 tokens)

### neverMask

```ts
neverMask: string[];
```

Defined in: context/observation-masker.ts:33

Tool names to NEVER mask (e.g., recall tools, state queries)
