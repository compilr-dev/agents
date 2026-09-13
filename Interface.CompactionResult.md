---
title: "CompactionResult"
parent: Interfaces
nav_order: 1
---


# Interface: CompactionResult

Defined in: context/types.ts:315

Result of a compaction operation

## Properties

### filesCreated

```ts
filesCreated: string[];
```

Defined in: context/types.ts:339

Files created during compaction (for reversibility)

### messagesAfter

```ts
messagesAfter: number;
```

Defined in: context/types.ts:324

Number of messages after compaction

### messagesBefore

```ts
messagesBefore: number;
```

Defined in: context/types.ts:319

Number of messages before compaction

### tokensAfter

```ts
tokensAfter: number;
```

Defined in: context/types.ts:334

Total tokens after compaction

### tokensBefore

```ts
tokensBefore: number;
```

Defined in: context/types.ts:329

Total tokens before compaction
