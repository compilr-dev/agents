---
title: "ContextStats"
parent: Interfaces
nav_order: 1
---


# Interface: ContextStats

Defined in: context/types.ts:538

Context statistics

## Properties

### compactionCount

```ts
compactionCount: number;
```

Defined in: context/types.ts:567

Number of compactions performed

### currentTokens

```ts
currentTokens: number;
```

Defined in: context/types.ts:542

Current token count

### maxTokens

```ts
maxTokens: number;
```

Defined in: context/types.ts:547

Maximum tokens allowed

### messageCount

```ts
messageCount: number;
```

Defined in: context/types.ts:557

Number of messages in history

### summarizationCount

```ts
summarizationCount: number;
```

Defined in: context/types.ts:572

Number of summarizations performed

### turnCount

```ts
turnCount: number;
```

Defined in: context/types.ts:562

Number of turns (user message + assistant response pairs)

### utilization

```ts
utilization: number;
```

Defined in: context/types.ts:552

Current utilization (0.0 - 1.0)
