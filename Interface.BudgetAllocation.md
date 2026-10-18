---
title: "BudgetAllocation"
parent: Interfaces
nav_order: 1
---


# Interface: BudgetAllocation

Defined in: context/types.ts:26

Budget allocation percentages for each category
Must sum to 1.0 (100%)

## Properties

### history

```ts
history: number;
```

Defined in: context/types.ts:49

Older conversation history allocation

#### Default

```ts
0.30 (30%)
```

### recentMessages

```ts
recentMessages: number;
```

Defined in: context/types.ts:37

Recent messages (last N turns) allocation

#### Default

```ts
0.40 (40%)
```

### system

```ts
system: number;
```

Defined in: context/types.ts:31

System prompt allocation

#### Default

```ts
0.05 (5%)
```

### toolResults

```ts
toolResults: number;
```

Defined in: context/types.ts:43

Tool results allocation

#### Default

```ts
0.25 (25%)
```
