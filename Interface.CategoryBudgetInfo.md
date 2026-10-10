---
title: "CategoryBudgetInfo"
parent: Interfaces
nav_order: 1
---


# Interface: CategoryBudgetInfo

Defined in: context/types.ts:55

Budget information for a single category

## Properties

### allocated

```ts
allocated: number;
```

Defined in: context/types.ts:59

Allocation fraction (0.0 - 1.0)

### allocatedTokens

```ts
allocatedTokens: number;
```

Defined in: context/types.ts:64

Allocated tokens based on maxContextTokens

### remaining

```ts
remaining: number;
```

Defined in: context/types.ts:74

Remaining tokens available

### used

```ts
used: number;
```

Defined in: context/types.ts:69

Currently used tokens in this category

### utilization

```ts
utilization: number;
```

Defined in: context/types.ts:79

Utilization of this category (0.0 - 1.0)
