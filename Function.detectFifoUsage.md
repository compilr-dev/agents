---
title: "detectFifoUsage"
parent: Functions
nav_order: 1
---


# Function: detectFifoUsage()

```ts
function detectFifoUsage(command): FifoDetectionResult;
```

Defined in: tools/builtin/bash.ts:125

Detect potential FIFO/named pipe usage in a command
Commands that read from FIFOs can hang indefinitely if no writer is available

## Parameters

| Parameter | Type |
| ------ | ------ |
| `command` | `string` |

## Returns

[`FifoDetectionResult`](Interface.FifoDetectionResult.md)
