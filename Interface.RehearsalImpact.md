---
title: "RehearsalImpact"
parent: Interfaces
nav_order: 1
---


# Interface: RehearsalImpact

Defined in: rehearsal/types.ts:64

Detailed impact analysis of a destructive operation

## Properties

### affectedFiles

```ts
affectedFiles: AffectedFile[];
```

Defined in: rehearsal/types.ts:78

List of affected files with details

### dataSize?

```ts
optional dataSize?: number;
```

Defined in: rehearsal/types.ts:94

Size of data that would be affected (in bytes)

### estimatedWorkHours?

```ts
optional estimatedWorkHours?: number;
```

Defined in: rehearsal/types.ts:89

Estimated hours of work that could be lost

### filesAffected

```ts
filesAffected: number;
```

Defined in: rehearsal/types.ts:68

Total number of files that would be affected

### linesAffected

```ts
linesAffected: number;
```

Defined in: rehearsal/types.ts:73

Total lines of code that would be changed/lost

### summary

```ts
summary: string;
```

Defined in: rehearsal/types.ts:99

Human-readable summary of the impact

### timeInvestment?

```ts
optional timeInvestment?: string;
```

Defined in: rehearsal/types.ts:84

Human-readable time investment summary
e.g., "Files modified in the last 2 hours"
