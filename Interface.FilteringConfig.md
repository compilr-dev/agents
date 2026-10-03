---
title: "FilteringConfig"
parent: Interfaces
nav_order: 1
---


# Interface: FilteringConfig

Defined in: context/types.ts:209

Filtering configuration - applied before adding to context

## Properties

### maxErrorLines

```ts
maxErrorLines: number;
```

Defined in: context/types.ts:227

Maximum lines for error traces

#### Default

```ts
50
```

### maxFileLines

```ts
maxFileLines: number;
```

Defined in: context/types.ts:221

Maximum lines for file content

#### Default

```ts
500
```

### maxToolResultTokens

```ts
maxToolResultTokens: number;
```

Defined in: context/types.ts:215

Maximum tokens for a single tool result
Results larger than this will be truncated

#### Default

```ts
80000
```
