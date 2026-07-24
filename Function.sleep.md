---
title: "sleep"
parent: Functions
nav_order: 1
---


# Function: sleep()

```ts
function sleep(ms, signal?): Promise<void>;
```

Defined in: utils/index.ts:22

Sleep for a specified duration, respecting AbortSignal

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `ms` | `number` | Duration in milliseconds |
| `signal?` | `AbortSignal` | Optional AbortSignal to cancel sleep |

## Returns

`Promise`\<`void`\>

## Throws

Error if signal is aborted
