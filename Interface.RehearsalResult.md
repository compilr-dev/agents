---
title: "RehearsalResult"
parent: Interfaces
nav_order: 1
---


# Interface: RehearsalResult

Defined in: rehearsal/types.ts:105

Result of rehearsing a destructive operation

## Properties

### alternatives?

```ts
optional alternatives?: string[];
```

Defined in: rehearsal/types.ts:149

Suggested safer alternatives (if any)

### analysisTimeMs

```ts
analysisTimeMs: number;
```

Defined in: rehearsal/types.ts:159

Time taken to perform the analysis (ms)

### category

```ts
category: OperationCategory;
```

Defined in: rehearsal/types.ts:114

Category of the operation

### impact

```ts
impact: RehearsalImpact;
```

Defined in: rehearsal/types.ts:129

Detailed impact analysis

### isDestructive

```ts
isDestructive: boolean;
```

Defined in: rehearsal/types.ts:119

Whether this operation is considered destructive

### isReversible

```ts
isReversible: boolean;
```

Defined in: rehearsal/types.ts:124

Whether the operation can be reversed/undone

### operation

```ts
operation: string;
```

Defined in: rehearsal/types.ts:109

The original operation/command being rehearsed

### recommendation

```ts
recommendation: RehearsalRecommendation;
```

Defined in: rehearsal/types.ts:144

Recommendation on how to proceed

### severity

```ts
severity: ImpactSeverity;
```

Defined in: rehearsal/types.ts:134

Severity of the potential impact

### warnings

```ts
warnings: string[];
```

Defined in: rehearsal/types.ts:139

Warning messages about potential issues

### workAtRisk?

```ts
optional workAtRisk?: WorkAtRisk;
```

Defined in: rehearsal/types.ts:154

Work episodes at risk from this operation (populated by episodic memory)
