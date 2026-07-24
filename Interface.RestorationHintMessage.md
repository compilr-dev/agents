---
title: "RestorationHintMessage"
parent: Interfaces
nav_order: 1
---


# Interface: RestorationHintMessage

Defined in: context/file-tracker.ts:112

A single restoration hint message for post-compaction context injection

## Properties

### path

```ts
path: string;
```

Defined in: context/file-tracker.ts:114

File path

### text

```ts
text: string;
```

Defined in: context/file-tracker.ts:120

The formatted hint text

### tokens

```ts
tokens: number;
```

Defined in: context/file-tracker.ts:123

Estimated token count of this hint

### type

```ts
type: "inline" | "reference";
```

Defined in: context/file-tracker.ts:117

Whether content is inlined or just referenced
