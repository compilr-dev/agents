---
title: "FilteringResult"
parent: Interfaces
nav_order: 1
---


# Interface: FilteringResult

Defined in: context/types.ts:380

Result of a filtering operation

## Properties

### filtered

```ts
filtered: boolean;
```

Defined in: context/types.ts:384

Whether the content was filtered

### filteredTokens

```ts
filteredTokens: number;
```

Defined in: context/types.ts:394

Token count after filtering

### originalTokens

```ts
originalTokens: number;
```

Defined in: context/types.ts:389

Original token count

### savedToFile?

```ts
optional savedToFile?: string;
```

Defined in: context/types.ts:399

Path to file where full content was saved (if filtered)
