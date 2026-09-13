---
title: "UsageTracker"
parent: Classes
nav_order: 1
---


# Class: UsageTracker

Defined in: costs/tracker.ts:47

UsageTracker tracks token usage across LLM calls

## Constructors

### Constructor

```ts
new UsageTracker(options?): UsageTracker;
```

Defined in: costs/tracker.ts:59

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `options` | [`UsageTrackerOptions`](Interface.UsageTrackerOptions.md) |

#### Returns

`UsageTracker`

## Accessors

### isEnabled

#### Get Signature

```ts
get isEnabled(): boolean;
```

Defined in: costs/tracker.ts:338

Check if tracking is enabled

##### Returns

`boolean`

### size

#### Get Signature

```ts
get size(): number;
```

Defined in: costs/tracker.ts:345

Get the number of records

##### Returns

`number`

## Methods

### formatTokens()

```ts
formatTokens(tokens): string;
```

Defined in: costs/tracker.ts:276

Format tokens with commas for display

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `tokens` | `number` |

#### Returns

`string`

### getBudgetStatus()

```ts
getBudgetStatus(): BudgetStatus;
```

Defined in: costs/tracker.ts:193

Get budget status

#### Returns

[`BudgetStatus`](Interface.BudgetStatus.md)

### getRecords()

```ts
getRecords(): readonly UsageRecord[];
```

Defined in: costs/tracker.ts:262

Get all records

#### Returns

readonly [`UsageRecord`](Interface.UsageRecord.md)[]

### getSessionRecords()

```ts
getSessionRecords(sessionId): UsageRecord[];
```

Defined in: costs/tracker.ts:269

Get records for a specific session

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `sessionId` | `string` |

#### Returns

[`UsageRecord`](Interface.UsageRecord.md)[]

### getSessionStats()

```ts
getSessionStats(sessionId): UsageStats;
```

Defined in: costs/tracker.ts:160

Get stats for a specific session

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `sessionId` | `string` |

#### Returns

[`UsageStats`](Interface.UsageStats.md)

### getStats()

```ts
getStats(): UsageStats;
```

Defined in: costs/tracker.ts:96

Get aggregated usage statistics

#### Returns

[`UsageStats`](Interface.UsageStats.md)

### getSummary()

```ts
getSummary(): string;
```

Defined in: costs/tracker.ts:283

Get a human-readable summary

#### Returns

`string`

### getTotalInputTokens()

```ts
getTotalInputTokens(): number;
```

Defined in: costs/tracker.ts:179

Get total input tokens

#### Returns

`number`

### getTotalOutputTokens()

```ts
getTotalOutputTokens(): number;
```

Defined in: costs/tracker.ts:186

Get total output tokens

#### Returns

`number`

### getTotalTokens()

```ts
getTotalTokens(): number;
```

Defined in: costs/tracker.ts:172

Get total tokens used

#### Returns

`number`

### isBudgetExceeded()

```ts
isBudgetExceeded(): boolean;
```

Defined in: costs/tracker.ts:224

Check if budget is exceeded

#### Returns

`boolean`

### onEvent()

```ts
onEvent(handler): () => void;
```

Defined in: costs/tracker.ts:317

Register an event handler

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `handler` | [`UsageEventHandler`](TypeAlias.UsageEventHandler.md) |

#### Returns

() => `void`

### record()

```ts
record(input): UsageRecord | undefined;
```

Defined in: costs/tracker.ts:68

Record token usage from an LLM call

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `input` | [`RecordUsageInput`](Interface.RecordUsageInput.md) |

#### Returns

[`UsageRecord`](Interface.UsageRecord.md) \| `undefined`

### reset()

```ts
reset(): void;
```

Defined in: costs/tracker.ts:252

Reset all tracking data

#### Returns

`void`
