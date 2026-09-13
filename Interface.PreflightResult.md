---
title: "PreflightResult"
parent: Interfaces
nav_order: 1
---


# Interface: PreflightResult

Defined in: context/types.ts:91

Result of a pre-flight context check

Call canAddContent() before adding content to check if action is needed.

## Properties

### action?

```ts
optional action?: "compact" | "summarize" | "reject";
```

Defined in: context/types.ts:105

Recommended action to take

### allowed

```ts
allowed: boolean;
```

Defined in: context/types.ts:95

Whether the content can be added without issues

### budgetRemaining

```ts
budgetRemaining: number;
```

Defined in: context/types.ts:120

Tokens remaining in the target category budget

### category?

```ts
optional category?: ContextCategory;
```

Defined in: context/types.ts:110

Which category needs action (for compact)

### estimatedTokens

```ts
estimatedTokens: number;
```

Defined in: context/types.ts:115

Estimated tokens for the content to add

### recommendation?

```ts
optional recommendation?: string;
```

Defined in: context/types.ts:125

Human-readable recommendation

### requiresAction

```ts
requiresAction: boolean;
```

Defined in: context/types.ts:100

Whether an action is required before adding
