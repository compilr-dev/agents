---
title: "DelegatedResultStore"
parent: Classes
nav_order: 1
---


# Class: DelegatedResultStore

Defined in: context/delegated-result-store.ts:34

In-memory store for delegated results with TTL expiration and LRU eviction.

## Constructors

### Constructor

```ts
new DelegatedResultStore(options?): DelegatedResultStore;
```

Defined in: context/delegated-result-store.ts:43

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `options?` | \{ `defaultTTL?`: `number`; `maxSize?`: `number`; \} |
| `options.defaultTTL?` | `number` |
| `options.maxSize?` | `number` |

#### Returns

`DelegatedResultStore`

## Methods

### add()

```ts
add(result): void;
```

Defined in: context/delegated-result-store.ts:58

Store a delegated result. Evicts oldest entries if at capacity.

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `result` | [`StoredResult`](Interface.StoredResult.md) |

#### Returns

`void`

### cleanup()

```ts
cleanup(): void;
```

Defined in: context/delegated-result-store.ts:97

Remove all expired entries.

#### Returns

`void`

### clear()

```ts
clear(): void;
```

Defined in: context/delegated-result-store.ts:110

Clear all stored results.

#### Returns

`void`

### generateId()

```ts
generateId(): string;
```

Defined in: context/delegated-result-store.ts:51

Generate a unique delegation ID.

#### Returns

`string`

### get()

```ts
get(id): StoredResult | undefined;
```

Defined in: context/delegated-result-store.ts:76

Get a stored result by ID. Returns undefined if not found or expired.

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |

#### Returns

[`StoredResult`](Interface.StoredResult.md) \| `undefined`

### getDefaultTTL()

```ts
getDefaultTTL(): number;
```

Defined in: context/delegated-result-store.ts:117

Get the default TTL for this store.

#### Returns

`number`

### getStats()

```ts
getStats(): DelegatedResultStoreStats;
```

Defined in: context/delegated-result-store.ts:124

Get store statistics.

#### Returns

[`DelegatedResultStoreStats`](Interface.DelegatedResultStoreStats.md)
