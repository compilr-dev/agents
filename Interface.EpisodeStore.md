---
title: "EpisodeStore"
parent: Interfaces
nav_order: 1
---


# Interface: EpisodeStore

Defined in: episodes/types.ts:215

Persistence interface for work episodes.
Write methods may be async (for file I/O), read methods are synchronous
(read from in-memory cache).

## Methods

### cleanup()

```ts
cleanup(maxAgeMs): number | Promise<number>;
```

Defined in: episodes/types.ts:247

Remove episodes older than maxAge milliseconds. Returns count removed.

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `maxAgeMs` | `number` |

#### Returns

`number` \| `Promise`\<`number`\>

### getAll()

```ts
getAll(): WorkEpisode[];
```

Defined in: episodes/types.ts:223

Get all episodes

#### Returns

[`WorkEpisode`](Interface.WorkEpisode.md)[]

### getByAgent()

```ts
getByAgent(agentId): WorkEpisode[];
```

Defined in: episodes/types.ts:229

Get episodes by agent ID

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `agentId` | `string` |

#### Returns

[`WorkEpisode`](Interface.WorkEpisode.md)[]

### getByFiles()

```ts
getByFiles(files): WorkEpisode[];
```

Defined in: episodes/types.ts:226

Get episodes for specific files

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `files` | `string`[] |

#### Returns

[`WorkEpisode`](Interface.WorkEpisode.md)[]

### getBySession()

```ts
getBySession(sessionId): WorkEpisode[];
```

Defined in: episodes/types.ts:232

Get episodes by session ID

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `sessionId` | `string` |

#### Returns

[`WorkEpisode`](Interface.WorkEpisode.md)[]

### getByTimeRange()

```ts
getByTimeRange(start, end): WorkEpisode[];
```

Defined in: episodes/types.ts:235

Get episodes within a time range (ISO timestamps)

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `start` | `string` |
| `end` | `string` |

#### Returns

[`WorkEpisode`](Interface.WorkEpisode.md)[]

### getRecent()

```ts
getRecent(count): WorkEpisode[];
```

Defined in: episodes/types.ts:238

Get the N most recent episodes

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `count` | `number` |

#### Returns

[`WorkEpisode`](Interface.WorkEpisode.md)[]

### getTotalEffort()

```ts
getTotalEffort(episodes?): Effort;
```

Defined in: episodes/types.ts:244

Get the maximum effort level across all episodes (or a subset)

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `episodes?` | [`WorkEpisode`](Interface.WorkEpisode.md)[] |

#### Returns

[`Effort`](TypeAlias.Effort.md)

### getWorkSummary()

```ts
getWorkSummary(): ProjectWorkSummary;
```

Defined in: episodes/types.ts:241

Get project work summary

#### Returns

[`ProjectWorkSummary`](Interface.ProjectWorkSummary.md)

### save()

```ts
save(episode): void | Promise<void>;
```

Defined in: episodes/types.ts:217

Save a single episode

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `episode` | [`WorkEpisode`](Interface.WorkEpisode.md) |

#### Returns

`void` \| `Promise`\<`void`\>

### saveBatch()

```ts
saveBatch(episodes): void | Promise<void>;
```

Defined in: episodes/types.ts:220

Save multiple episodes at once

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `episodes` | [`WorkEpisode`](Interface.WorkEpisode.md)[] |

#### Returns

`void` \| `Promise`\<`void`\>
