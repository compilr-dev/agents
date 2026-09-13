---
title: "RehearsalManagerOptions"
parent: Interfaces
nav_order: 1
---


# Interface: RehearsalManagerOptions

Defined in: rehearsal/types.ts:235

Options for the RehearsalManager

## Properties

### analyzers?

```ts
optional analyzers?: RehearsalAnalyzer[];
```

Defined in: rehearsal/types.ts:244

Custom analyzers to add

### includeBuiltinAnalyzers?

```ts
optional includeBuiltinAnalyzers?: boolean;
```

Defined in: rehearsal/types.ts:249

Whether to include built-in analyzers (default: true)

### onRehearsal?

```ts
optional onRehearsal?: (result) => void;
```

Defined in: rehearsal/types.ts:259

Callback when a rehearsal is performed

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `result` | [`RehearsalResult`](Interface.RehearsalResult.md) |

#### Returns

`void`

### sessionStartTime?

```ts
optional sessionStartTime?: Date;
```

Defined in: rehearsal/types.ts:264

Session start time for time investment calculations

### trackSessionFiles?

```ts
optional trackSessionFiles?: boolean;
```

Defined in: rehearsal/types.ts:269

Track files modified during session

### warningThreshold?

```ts
optional warningThreshold?: ImpactSeverity;
```

Defined in: rehearsal/types.ts:254

Minimum severity to trigger warnings (default: 'medium')

### workingDirectory?

```ts
optional workingDirectory?: string;
```

Defined in: rehearsal/types.ts:239

Working directory (defaults to process.cwd())
