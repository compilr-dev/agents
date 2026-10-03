---
title: "BudgetStatus"
parent: Interfaces
nav_order: 1
---


# Interface: BudgetStatus

Defined in: costs/types.ts:98

Budget status

## Properties

### currentInputTokens

```ts
currentInputTokens: number;
```

Defined in: costs/types.ts:102

Current input tokens

### currentOutputTokens

```ts
currentOutputTokens: number;
```

Defined in: costs/types.ts:104

Current output tokens

### currentTokens

```ts
currentTokens: number;
```

Defined in: costs/types.ts:100

Current total tokens

### exceeded

```ts
exceeded: boolean;
```

Defined in: costs/types.ts:110

Whether budget is exceeded

### tokenLimit?

```ts
optional tokenLimit?: number;
```

Defined in: costs/types.ts:106

Token limit (if set)

### tokenUtilization?

```ts
optional tokenUtilization?: number;
```

Defined in: costs/types.ts:108

Token utilization (0-1)

### warning

```ts
warning: boolean;
```

Defined in: costs/types.ts:112

Whether warning threshold is reached
