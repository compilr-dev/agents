---
title: "SummarizationConfig"
parent: Interfaces
nav_order: 1
---


# Interface: SummarizationConfig

Defined in: context/types.ts:262

Summarization configuration - compresses entire history

## Properties

### emergencyPreserveMessages

```ts
emergencyPreserveMessages: number;
```

Defined in: context/types.ts:291

Number of recent messages to preserve in emergency mode

#### Default

```ts
4
```

### emergencyThreshold

```ts
emergencyThreshold: number;
```

Defined in: context/types.ts:279

Trigger emergency summarization (fewer preserved messages)

#### Default

```ts
0.95 (95%)
```

### maxRounds

```ts
maxRounds: number;
```

Defined in: context/types.ts:303

Maximum summarization rounds before throwing error

#### Default

```ts
3
```

### preserveRecentMessages

```ts
preserveRecentMessages: number;
```

Defined in: context/types.ts:285

Number of recent messages to preserve in normal mode

#### Default

```ts
6
```

### summaryMaxTokens

```ts
summaryMaxTokens: number;
```

Defined in: context/types.ts:297

Maximum tokens for the summary

#### Default

```ts
2000
```

### targetUtilization

```ts
targetUtilization: number;
```

Defined in: context/types.ts:309

Target utilization after summarization

#### Default

```ts
0.70 (70%)
```

### triggerThreshold

```ts
triggerThreshold: number;
```

Defined in: context/types.ts:273

Trigger normal summarization when context utilization exceeds this threshold

#### Default

```ts
0.90 (90%)
```

### warningThreshold

```ts
warningThreshold: number;
```

Defined in: context/types.ts:267

Emit warning when context utilization exceeds this threshold

#### Default

```ts
0.80 (80%)
```
