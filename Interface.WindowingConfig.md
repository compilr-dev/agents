---
title: "WindowingConfig"
parent: Interfaces
nav_order: 1
---


# Interface: WindowingConfig

Defined in: context/windowing.ts:23

## Properties

### enabled

```ts
enabled: boolean;
```

Defined in: context/windowing.ts:29

Whether windowing is enabled. Default: true

### recentWindowTokens

```ts
recentWindowTokens: number;
```

Defined in: context/windowing.ts:27

Tokens reserved for recent window (never compacted). Default: 15000

### targetHistoryTokens

```ts
targetHistoryTokens: number;
```

Defined in: context/windowing.ts:25

Target maximum tokens for conversation history. Default: 60000
