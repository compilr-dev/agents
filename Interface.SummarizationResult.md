---
title: "SummarizationResult"
parent: Interfaces
nav_order: 1
---


# Interface: SummarizationResult

Defined in: context/types.ts:345

Result of a summarization operation

## Properties

### emergency

```ts
emergency: boolean;
```

Defined in: context/types.ts:374

Whether emergency mode was used

### messagesPreserved

```ts
messagesPreserved: number;
```

Defined in: context/types.ts:359

Number of messages preserved (not summarized)

### originalTokens

```ts
originalTokens: number;
```

Defined in: context/types.ts:349

Tokens in original conversation

### rounds

```ts
rounds: number;
```

Defined in: context/types.ts:369

Number of summarization rounds performed

### summary

```ts
summary: string;
```

Defined in: context/types.ts:364

The generated summary text

### summaryTokens

```ts
summaryTokens: number;
```

Defined in: context/types.ts:354

Tokens in summary
