---
title: "calculateBackoffDelay"
parent: Functions
nav_order: 1
---


# Function: calculateBackoffDelay()

```ts
function calculateBackoffDelay(
   attempt, 
   baseDelayMs?, 
   maxDelayMs?): number;
```

Defined in: utils/index.ts:138

Calculate delay with exponential backoff and jitter

## Parameters

| Parameter | Type | Default value | Description |
| ------ | ------ | ------ | ------ |
| `attempt` | `number` | `undefined` | Current attempt number (0-indexed) |
| `baseDelayMs` | `number` | `DEFAULT_RETRY_CONFIG.baseDelayMs` | Base delay in milliseconds |
| `maxDelayMs` | `number` | `DEFAULT_RETRY_CONFIG.maxDelayMs` | Maximum delay cap in milliseconds |

## Returns

`number`

Delay in milliseconds
