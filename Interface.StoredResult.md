---
title: "StoredResult"
parent: Interfaces
nav_order: 1
---


# Interface: StoredResult

Defined in: context/delegation-types.ts:46

A stored full result that was replaced by a summary.

## Properties

### expiresAt

```ts
expiresAt: number;
```

Defined in: context/delegation-types.ts:72

Timestamp when this result expires

### fullContent

```ts
fullContent: string;
```

Defined in: context/delegation-types.ts:57

The full serialized result content

### fullTokens

```ts
fullTokens: number;
```

Defined in: context/delegation-types.ts:60

Token count of the full content

### id

```ts
id: string;
```

Defined in: context/delegation-types.ts:48

Unique delegation ID, e.g., 'dr_1707900000_0'

### storedAt

```ts
storedAt: number;
```

Defined in: context/delegation-types.ts:69

Timestamp when stored

### summary

```ts
summary: string;
```

Defined in: context/delegation-types.ts:63

The generated summary

### summaryTokens

```ts
summaryTokens: number;
```

Defined in: context/delegation-types.ts:66

Token count of the summary

### toolInput

```ts
toolInput: Record<string, unknown>;
```

Defined in: context/delegation-types.ts:54

Input parameters passed to the tool

### toolName

```ts
toolName: string;
```

Defined in: context/delegation-types.ts:51

Name of the tool that produced the result
