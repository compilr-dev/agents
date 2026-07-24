---
title: "FifoDetectionResult"
parent: Interfaces
nav_order: 1
---


# Interface: FifoDetectionResult

Defined in: tools/builtin/bash.ts:104

FIFO detection result

## Properties

### detected

```ts
detected: boolean;
```

Defined in: tools/builtin/bash.ts:108

Whether potential FIFO/pipe usage was detected

### patterns

```ts
patterns: string[];
```

Defined in: tools/builtin/bash.ts:113

Patterns that matched

### warning?

```ts
optional warning?: string;
```

Defined in: tools/builtin/bash.ts:118

Warning message to display
