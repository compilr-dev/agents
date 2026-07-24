---
title: "GitRehearsalAnalyzer"
parent: Classes
nav_order: 1
---


# Class: GitRehearsalAnalyzer

Defined in: rehearsal/git-analyzer.ts:477

Git Rehearsal Analyzer

## Implements

- [`RehearsalAnalyzer`](Interface.RehearsalAnalyzer.md)

## Constructors

### Constructor

```ts
new GitRehearsalAnalyzer(): GitRehearsalAnalyzer;
```

#### Returns

`GitRehearsalAnalyzer`

## Properties

### category

```ts
readonly category: "git";
```

Defined in: rehearsal/git-analyzer.ts:480

Category of operations this analyzer handles

#### Implementation of

[`RehearsalAnalyzer`](Interface.RehearsalAnalyzer.md).[`category`](Interface.RehearsalAnalyzer.md#category)

### id

```ts
readonly id: "git-analyzer" = 'git-analyzer';
```

Defined in: rehearsal/git-analyzer.ts:478

Unique identifier for this analyzer

#### Implementation of

[`RehearsalAnalyzer`](Interface.RehearsalAnalyzer.md).[`id`](Interface.RehearsalAnalyzer.md#id)

### name

```ts
readonly name: "Git Operations Analyzer" = 'Git Operations Analyzer';
```

Defined in: rehearsal/git-analyzer.ts:479

Human-readable name

#### Implementation of

[`RehearsalAnalyzer`](Interface.RehearsalAnalyzer.md).[`name`](Interface.RehearsalAnalyzer.md#name)

### patterns

```ts
readonly patterns: RegExp[] = GIT_DESTRUCTIVE_PATTERNS;
```

Defined in: rehearsal/git-analyzer.ts:481

Patterns that this analyzer can handle

#### Implementation of

[`RehearsalAnalyzer`](Interface.RehearsalAnalyzer.md).[`patterns`](Interface.RehearsalAnalyzer.md#patterns)

## Methods

### analyze()

```ts
analyze(operation, context): Promise<RehearsalResult>;
```

Defined in: rehearsal/git-analyzer.ts:487

Analyze the operation and return impact assessment

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `operation` | `string` |
| `context` | [`RehearsalContext`](Interface.RehearsalContext.md) |

#### Returns

`Promise`\<[`RehearsalResult`](Interface.RehearsalResult.md)\>

#### Implementation of

[`RehearsalAnalyzer`](Interface.RehearsalAnalyzer.md).[`analyze`](Interface.RehearsalAnalyzer.md#analyze)

### canAnalyze()

```ts
canAnalyze(operation): boolean;
```

Defined in: rehearsal/git-analyzer.ts:483

Check if this analyzer can handle the given operation

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `operation` | `string` |

#### Returns

`boolean`

#### Implementation of

[`RehearsalAnalyzer`](Interface.RehearsalAnalyzer.md).[`canAnalyze`](Interface.RehearsalAnalyzer.md#cananalyze)
