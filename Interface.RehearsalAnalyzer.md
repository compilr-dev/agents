---
title: "RehearsalAnalyzer"
parent: Interfaces
nav_order: 1
---


# Interface: RehearsalAnalyzer

Defined in: rehearsal/types.ts:200

Interface for operation-specific analyzers

## Properties

### category

```ts
readonly category: OperationCategory;
```

Defined in: rehearsal/types.ts:214

Category of operations this analyzer handles

### id

```ts
readonly id: string;
```

Defined in: rehearsal/types.ts:204

Unique identifier for this analyzer

### name

```ts
readonly name: string;
```

Defined in: rehearsal/types.ts:209

Human-readable name

### patterns

```ts
readonly patterns: RegExp[];
```

Defined in: rehearsal/types.ts:219

Patterns that this analyzer can handle

## Methods

### analyze()

```ts
analyze(operation, context): Promise<RehearsalResult>;
```

Defined in: rehearsal/types.ts:229

Analyze the operation and return impact assessment

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `operation` | `string` |
| `context` | [`RehearsalContext`](Interface.RehearsalContext.md) |

#### Returns

`Promise`\<[`RehearsalResult`](Interface.RehearsalResult.md)\>

### canAnalyze()

```ts
canAnalyze(operation): boolean;
```

Defined in: rehearsal/types.ts:224

Check if this analyzer can handle the given operation

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `operation` | `string` |

#### Returns

`boolean`
