---
title: "DelegatedResultStoreStats"
parent: Interfaces
nav_order: 1
---


# Interface: DelegatedResultStoreStats

Defined in: context/delegated-result-store.ts:14

Statistics about the delegation store.

## Properties

### maxSize

```ts
maxSize: number;
```

Defined in: context/delegated-result-store.ts:19

Maximum capacity (LRU limit)

### size

```ts
size: number;
```

Defined in: context/delegated-result-store.ts:16

Number of currently stored results

### totalEvicted

```ts
totalEvicted: number;
```

Defined in: context/delegated-result-store.ts:25

Total results evicted (TTL or LRU)

### totalRecalled

```ts
totalRecalled: number;
```

Defined in: context/delegated-result-store.ts:28

Total results successfully recalled

### totalStored

```ts
totalStored: number;
```

Defined in: context/delegated-result-store.ts:22

Total results stored since creation
