---
title: "WindowingResult"
parent: Interfaces
nav_order: 1
---


# Interface: WindowingResult

Defined in: context/windowing.ts:65

## Properties

### applied

```ts
applied: boolean;
```

Defined in: context/windowing.ts:67

Whether windowing was applied

### importanceCounts

```ts
importanceCounts: Record<ImportanceLevel, number>;
```

Defined in: context/windowing.ts:81

Importance distribution

### messages

```ts
messages: Message[];
```

Defined in: context/windowing.ts:69

Messages after windowing

### tokensAfter

```ts
tokensAfter: number;
```

Defined in: context/windowing.ts:73

Tokens after windowing

### tokensBefore

```ts
tokensBefore: number;
```

Defined in: context/windowing.ts:71

Tokens before windowing

### zones

```ts
zones: {
  middle: number;
  old: number;
  recent: number;
};
```

Defined in: context/windowing.ts:75

Zone sizes

#### middle

```ts
middle: number;
```

#### old

```ts
old: number;
```

#### recent

```ts
recent: number;
```
