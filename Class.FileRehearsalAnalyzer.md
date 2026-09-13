---
title: "FileRehearsalAnalyzer"
parent: Classes
nav_order: 1
---


# Class: FileRehearsalAnalyzer

Defined in: rehearsal/file-analyzer.ts:311

File Rehearsal Analyzer

## Implements

- [`RehearsalAnalyzer`](Interface.RehearsalAnalyzer.md)

## Constructors

### Constructor

```ts
new FileRehearsalAnalyzer(): FileRehearsalAnalyzer;
```

#### Returns

`FileRehearsalAnalyzer`

## Properties

### category

```ts
readonly category: "file";
```

Defined in: rehearsal/file-analyzer.ts:314

Category of operations this analyzer handles

#### Implementation of

[`RehearsalAnalyzer`](Interface.RehearsalAnalyzer.md).[`category`](Interface.RehearsalAnalyzer.md#category)

### id

```ts
readonly id: "file-analyzer" = 'file-analyzer';
```

Defined in: rehearsal/file-analyzer.ts:312

Unique identifier for this analyzer

#### Implementation of

[`RehearsalAnalyzer`](Interface.RehearsalAnalyzer.md).[`id`](Interface.RehearsalAnalyzer.md#id)

### name

```ts
readonly name: "File Operations Analyzer" = 'File Operations Analyzer';
```

Defined in: rehearsal/file-analyzer.ts:313

Human-readable name

#### Implementation of

[`RehearsalAnalyzer`](Interface.RehearsalAnalyzer.md).[`name`](Interface.RehearsalAnalyzer.md#name)

### patterns

```ts
readonly patterns: RegExp[] = FILE_DESTRUCTIVE_PATTERNS;
```

Defined in: rehearsal/file-analyzer.ts:315

Patterns that this analyzer can handle

#### Implementation of

[`RehearsalAnalyzer`](Interface.RehearsalAnalyzer.md).[`patterns`](Interface.RehearsalAnalyzer.md#patterns)

## Methods

### analyze()

```ts
analyze(operation, context): Promise<RehearsalResult>;
```

Defined in: rehearsal/file-analyzer.ts:321

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

Defined in: rehearsal/file-analyzer.ts:317

Check if this analyzer can handle the given operation

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `operation` | `string` |

#### Returns

`boolean`

#### Implementation of

[`RehearsalAnalyzer`](Interface.RehearsalAnalyzer.md).[`canAnalyze`](Interface.RehearsalAnalyzer.md#cananalyze)
